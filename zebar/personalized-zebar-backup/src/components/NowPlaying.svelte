<script lang="ts">
  import type { GlazeWmOutput, MediaOutput } from "zebar";

  import Group from "../components/Group.svelte";
  import Button from "./Button.svelte";

  type RightGroupProps = {
    glazewm: GlazeWmOutput;
    media: MediaOutput;
  };

  let { glazewm, media }: RightGroupProps = $props();
</script>

<!-- Media detection -->
{#if media && media.currentSession}
  <Group class="shrink-0">
    <div class="flex items-center gap-1 right-group-element">
      <Button
        iconClass={media.currentSession.isPlaying
          ? "player-pause"
          : "player-play"}
        class={media.currentSession.isPlaying
          ? "text-zb-now-playing"
          : "text-zb-not-playing"}
        noBg={true}
        callback={() =>
          media.togglePlayPause({ sessionId: media.currentSession!.sessionId })}
      ></Button>
      <div class="max-w-xs overflow-hidden group">
        <div class="inline-block whitespace-nowrap group-hover:animate-marquee">
          <span>
            {media.currentSession.title || "unknown"}
            {#if media.currentSession.artist}
              - {media.currentSession.artist}
            {/if}
          </span>
        </div>
      </div>
    </div>
  </Group>
  <!-- Fallback for Opera YouTube -->
{:else}
  {#each glazewm?.allWindows as window}
    {#if window.type == "window" && window.title.includes("YouTube")}
      <Group class="shrink-0">
        <div class="flex items-center gap-1 right-group-element">
          <Button
            iconClass="player-play"
            class="text-zb-now-playing"
            noBg={true}
            callback={() => {}}
          ></Button>
          <div class="max-w-xs overflow-hidden group">
            <div
              class="inline-block whitespace-nowrap group-hover:animate-marquee"
            >
              <span>
                {window.title
                  .replace(/ - YouTube.*/, "")
                  .replace("- Opera", "") || "unknown"}
              </span>
            </div>
          </div>
        </div>
      </Group>
    {/if}
  {/each}
{/if}
