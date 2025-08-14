<script lang="ts">
  import type {
    DateOutput,
    WeatherOutput
  } from "zebar";

  type RightGroupProps = {
    date: DateOutput;
    weather: WeatherOutput;
  };

  let { date, weather }: RightGroupProps = $props();

</script>

<div class="flex items-center gap-3 pr-2">
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
