<script lang="ts">
  import type {
    DateOutput,
    NetworkOutput,
    WeatherOutput
  } from "zebar";

  type RightGroupProps = {
    date: DateOutput;
    network: NetworkOutput;
    weather: WeatherOutput;
  };

  let { date, network, weather }: RightGroupProps = $props();

</script>

<div class="flex items-center gap-3 pr-2">
  <div class="flex items-center gap-1 right-group-element">
    {#if network?.defaultInterface?.type === "ethernet"}
      <i class="ti ti-network"></i>
    {:else if network?.defaultInterface?.type === "wifi"}
      {#if network.defaultGateway!.signalStrength! >= 75}
        <i class="ti ti-wifi"></i>
      {:else if network.defaultGateway!.signalStrength! >= 50}
        <i class="ti ti-wifi-2"></i>
      {:else if network.defaultGateway!.signalStrength! >= 25}
        <i class="ti ti-wifi-1"></i>
      {:else}
        <i class="ti ti-wifi-off"></i>
      {/if}
      {#if network?.defaultGateway?.ssid}
        <div class="overflow-hidden max-w-20 group">
          <div
            class="inline-block whitespace-nowrap group-hover:animate-marquee"
          >
            <span>
              {network.defaultGateway.ssid}
            </span>
          </div>
        </div>
      {/if}
    {:else}
      <i class="ti ti-wifi-off"></i>
    {/if}
  </div>
  {#if weather}
    <div class="flex items-center gap-1 right-group-element">
      {#if weather.status === "clear_day"}
        <i class="nf nf-weather-day_sunny weather-icon weather-sun"></i>
      {:else if weather.status === "clear_night"}
        <i class="nf nf-weather-night_clear weather-icon weather-moon"></i>
      {:else if weather.status === "cloudy_day"}
        <i class="nf nf-weather-day_cloudy weather-icon weather-cloud"></i>
      {:else if weather.status === "cloudy_night"}
        <i class="nf nf-weather-night_alt_cloudy weather-icon weather-cloud"></i>
      {:else if weather.status === "light_rain_day"}
        <i class="nf nf-weather-day_sprinkle weather-icon weather-rain"></i>
      {:else if weather.status === "light_rain_night"}
        <i class="nf nf-weather-night_alt_sprinkle weather-icon weather-rain"></i>
      {:else if weather.status === "heavy_rain_day"}
        <i class="nf nf-weather-day_rain weather-icon weather-rain"></i>
      {:else if weather.status === "heavy_rain_night"}
        <i class="nf nf-weather-night_alt_rain weather-icon weather-rain"></i>
      {:else if weather.status === "snow_day"}
        <i class="nf nf-weather-day_snow weather-icon weather-snow"></i>
      {:else if weather.status === "snow_night"}
        <i class="nf nf-weather-night_alt_snow weather-icon weather-snow"></i>
      {:else if weather.status === "thunder_day"}
        <i class="nf nf-weather-day_lightning weather-icon weather-thunder"></i>
      {:else if weather.status === "thunder_night"}
        <i class="nf nf-weather-night_alt_lightning weather-icon weather-thunder"></i>
      {/if}
      {Math.round(weather.celsiusTemp)}°
    </div>
  {/if}
  <div class="flex items-center gap-1 right-group-element">
    {date?.formatted}
  </div>
</div>
