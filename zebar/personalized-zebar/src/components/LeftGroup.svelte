<script lang="ts">
  import type {
    CpuOutput,
    MemoryOutput,
    GlazeWmOutput,
    AudioOutput,
    NetworkOutput
  } from "zebar";

  import Button from "./Button.svelte";
  import Meter from "./Meter.svelte";

  type LeftGroupProps = {
    cpu: CpuOutput;
    memory: MemoryOutput;
    glazewm: GlazeWmOutput;
    audio: AudioOutput;
    network: NetworkOutput;
  };

  let { cpu, memory, glazewm, audio, network }: LeftGroupProps = $props();

  function getVolumeClass(volume: number): string {
    if (volume === 0) return "bg-zb-volume-muted";
    if (volume <= 33) return "bg-zb-volume-low";
    if (volume <= 66) return "bg-zb-volume-medium";
    return "bg-zb-volume-high";
  }


  function getCpuClass(usage: number): string {
    if (usage >= 80) return "bg-zb-cpu-high-usage";
    return "bg-zb-cpu";
  }

  function getMemoryClass(usage: number): string {
    if (usage <= 50) return "bg-zb-memory-low";
    if (usage <= 75) return "bg-zb-memory-medium";
    return "bg-zb-memory-high";
  }

  function getNetworkClass(activityPercent: number): string {
    if (activityPercent <= 25) return "bg-zb-network-low";
    if (activityPercent <= 60) return "bg-zb-network-medium";
    return "bg-zb-network-high";
  }

  function calculateNetworkActivity(): number {
    if (!network) return 30; // Show some activity if network data isn't available
    
    // Check if we have a default interface
    if (network.defaultInterface?.type === "wifi") {
      // Use signal strength for WiFi if available
      const signalStrength = network.defaultGateway?.signalStrength;
      if (signalStrength !== undefined && signalStrength !== null) {
        return Math.round(signalStrength);
      }
      return 60; // Default WiFi activity
    } else if (network.defaultInterface?.type === "ethernet") {
      // For ethernet, show high activity
      return 85;
    }
    
    // Fallback: show moderate activity
    return 45;
  }
</script>

<div class="flex flex-row items-center gap-3">
  <Button
    class="text-zb-power"
    iconClass="power"
    callback={() => glazewm!.runCommand("shell-exec shutdown /s /t 0")}
  />
  <Button
    class="text-zb-restart"
    iconClass="refresh"
    callback={() => glazewm!.runCommand("shell-exec shutdown /r /t 0")}
  />
  <div class="flex items-center gap-1">
    <i class="ti ti-ruler-2"></i>
    <Meter
      class={getMemoryClass(Math.round(memory?.usage ?? 0))}
      percent={Math.round(memory?.usage ?? 0)}
    />
  </div>
  <div class="flex items-center gap-1">
    <i class="ti ti-cpu"></i>
    <Meter
      class={getCpuClass(Math.round(cpu?.usage ?? 0))}
      percent={Math.round(cpu?.usage ?? 0)}
    />
  </div>
  <div class="flex items-center gap-1">
    <i class="ti ti-volume"></i>
    <Meter
      class={getVolumeClass(
        Math.round(audio?.defaultPlaybackDevice?.volume ?? 0)
      )}
      percent={Math.round(audio?.defaultPlaybackDevice?.volume ?? 0)}
    />
  </div>
  <div class="flex items-center gap-1">
    <i class="ti ti-network"></i>
    <Meter
      class={getNetworkClass(calculateNetworkActivity())}
      percent={calculateNetworkActivity()}
    />
  </div>
</div>
