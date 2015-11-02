---
title: 'Day 5: Weather Component'
author: bear
layout: post
permalink: /2011/03/02/day-5-weather-component/
aktt_notify_twitter:
  - yes
aktt_tweeted:
  - 1
categories:
  - Custom Skinnable Components
  - Moderate
---
Howdy doody, here's a weather component. It displays the forecast for up to the next 7 days. In this case, the skinnable component is using the zip code "94103" -- that's San Francisco, so there's a good chance for rain.

Click the image to view the running example.

[<img class="aligncenter size-full wp-image-554" title="WeatherProject" src="http://flashcats.net/wp-content/uploads/2011/03/WeatherProject.png" alt="" width="511" height="249" />][1]

The project is available [here][2]. There's an overall weather component that takes a zip code, and provides information for up to seven single day forecast components. It is currently pulled from the [NOAA][3] weather forecast service. Happy forecasting!

Details after the jump

<!--more-->

This skinnable component requires Flash Catalyst Panini or higher.

The WeatherComponent has the following skin parts

  * Zip: A RichText skin part taking a zip code for the forecast
  * Day[0-6], WeatherComponentSingleDays, each representing the forecast for a 24 hour period

The WeatherComponentSingleDay component has the following skin parts. If they exist in a skin, they are dynamically populated at runtime.

  * Forecast Period: The day of the week the forecast is for.
  * Forecast Conditions: A summary of the forecast (eg "Slight Chance Rain").
  * Temp High F/C: Forecast high temperature in Fahrenheit / Celsius.
  * Temp Low F/C: Forecast low temperature in Fahrenheit / Celsius.

The WeatherComponentSingleDay has several states, each corresponding to a general weather condition. There are many different weather classifications; this component condenses them into a reasonable number of visual states.

Update: There is a bug for some NOAA forecasts, where the component doesn't update its text fields. I'll get a fix in when I can.

 [1]: /static/skinnable-weather-component/Main.swf
 [2]: http://dl.dropbox.com/u/21428091/WeatherProject.fxp
 [3]: http://weather.gov