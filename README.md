### &lt;my-highcharts&gt;

 - [Polymer](https://www.polymer-project.org/1.0/) custom web component
 - [Highcharts API](http://highcharts.com)
 - [Highcharts free to non-commercial license](http://highcharts.com/)
 - Developer: [Michael Rosata](mailto:mrosata1984@gmail.com)


#### Pie Charts
Pie charts are awesome! Now you can slice up awesome pie on the fly.
![Pie Charts with HighCharts and My-Highchart](https://github.com/mrosata/my-highchart/master/public/pie-chart.jpg "Pie Charts with my-highchart")
```html
<my-highchart type="pie" title="How News Readers Read News (2015)">
    <pie-data name="Desktop" y="18" selected="true"></pie-data>
    <pie-data name="Laptop" y="12"></pie-data>
    <pie-data name="Tablet" y="40" sliced="true"></pie-data>
    <pie-data name="Phone" y="17"></pie-data>
    <pie-data name="Paper" y="3"></pie-data>
</my-highchart>
```

#### Bar Charts
`<my-highchart>` lowers the bar of difficulty to create a bar chart on the fly while maintaining the high bar of quality already found within the HighCharts API. Nothing is required besides data, about everything else could be left out. Data is set using the arrays written as plain text inside each `<set-data>` element, that is where you set data in JSON format. The last `<set-data>` has an object which says "for this dataset find the mean of data matching css selector `.medal`". That selector is an optional way to tell the web component to do a common calculation using data from a collection of `<data-set>` elements used in the chart. It makes use of querySelectorAll() and only matches elements inside the current `<my-highchart>` parent element.
![A bar chart created using my-highchart and HighCharts JavaScript API](https://github.com/mrosata/my-highchart/master/public/bar-chart.jpg "Bar Chart")
```html
<my-highchart x-label="Sporting Competitions" y-label="Medals" categories='["Soccer","Basketball","Football"]'>
    <set-data class="medal" name="Gold" color="gold">[13,2,3]</set-data>
    <set-data class="medal" name="Silver" color="#45AB6A">[11,13,9]</set-data>
    <set-data class="medal" name="Bronze">[5,3,6]</set-data>
    <set-data name="Averages" type="spline">{"mean":".medal"}</set-data>
</my-highchart>
```

#### Column Charts
Very similiar to the bar chart except in the way it is displayed. This example is a little more complex, but only in the size of the example and not in the properties in the html. You still have access to any properties used in the bar charts such as `color` and `x-label`, `y-label`. Play around, we are in the early state but still do a lot thanks to the great Polymer and HighCharts code bases.
![Column Chart with HighCharts and My Highchart](https://github.com/mrosata/my-highchart/master/public/column-chart.jpg "Column Chart")
```html
<my-highchart type="column" categories='["2011","2012","2013","2014","2015"]' title="Yearly Benchmark Testing Across Top Mobile Industry Brands" width="1000">
    <set-data class="android" name="And. Speed" >[99,42,51,67,89]</set-data>
    <set-data class="android" name="And. Memory">[80,33,59,60,62]</set-data>
    <set-data class="android" name="And. Storage">[55,15,36, 50,70]</set-data>
    <set-data class="windows" name="Speed">[21,55,42, 50,47]</set-data>
    <set-data class="windows" name="Win. Memory">[35,45,55, 50,71]</set-data>
    <set-data class="windows" name="Win. Storage">[28,85,86, 50,17]</set-data>
    <set-data class="apple" name="Speed">[89,35,66, 90,60]</set-data>
    <set-data class="apple" name="iPhone Memory">[16,45,25, 68,40]</set-data>
    <set-data class="apple" name="iPhone Storage">[65,5,53, 70,84]</set-data>
    
    <set-data name="Android Averages" type="spline">{"mean":".android"}</set-data>
    <set-data name="Windows Averages" type="spline">{"mean":".windows"}</set-data>
    <set-data name="Apple Averages" type="spline">{"mean":".apple"}</set-data>
</my-highchart>
```

I will release documentation as development moves forward. Feel free to fork and mix it up. Have fun, Polymer is awesome and so is HighCharts. Please always remember that licenses should be followed. I share my code free for anyone, but HighCharts is only free for non-commercial use. The &lt;my-highchart&gt; custom element makes HighCharts charts easily created, but there is much more amazing functionality found in the documents at [HighCharts Documentation](http://www.highcharts.com/docs) and none of that great functionality or use is limited or altered in any way by "My HighCharts".
