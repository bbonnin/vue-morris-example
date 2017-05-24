<template>
  <div id="app">
    <div class="container">
      <div class="page-header">
        <h2>Vue-Morris examples</h2>
        <p><a href="https://github.com/bbonnin/vue-morris">Vue-morris</a> component wraps the charts library <a href="http://morrisjs.github.io/morris.js/">Morris.js</a>. As the attributes used in this component have the same name than in Morris.js, you will find more details in its documentation (don't forget: if an option has upper cases, such as barColors, you have to use bar-colors in html).</p>
      </div>
      <div class="row">

        <div class="col-xs-12 panel panel-default">
          <div class="panel-body">
            <div class="col-sm-6">
              <h3>Bar Chart</h3>
              <bar-chart 
                id="bar" :data="barData" xkey="year" ykeys='[ "and", "ios", "win" ]' resize="true"
                labels='[ "Android", "iOS", "Windows" ]' bar-colors='[ "#FF6384", "#36A2EB", "#FFCE56" ]'
                grid="true" grid-text-weight="bold">
              </bar-chart>
            </div>
            <div class="col-sm-6">
              <pre style="border:none; background-color:white">
                <code class="xml">
  &lt;bar-chart 
    id="bar"
    data='[
        { "year": "2013", "and": 10, "ios": 5, "win": 2 },
        { "year": "2014", "and": 10, "ios": 15, "win": 3 },
        { "year": "2015", "and": 20, "ios": 25, "win": 2 },
        { "year": "2016", "and": 30, "ios": 20, "win": 1 },
      ]'
    xkey="year"
    ykeys='[ "and", "ios", "win" ]'
    bar-colors='[ "#FF6384", "#36A2EB", "#FFCE56" ]' 
    grid="true"
    grid-text-weight="bold"
    resize="true"&gt;
  &lt;/bar-chart&gt;
                </code>
              </pre>
            </div>
          </div>
        </div>

        <div class="col-xs-12 panel panel-default">
          <div class="panel-body">
            <div class="col-sm-6">
              <h3>Line Chart <small>(with values modified every 5 seconds)</small></h3>
              <div v-if="lineData.length != 0">
                <line-chart
                  id="line" :data="lineData" xkey="year" ykeys='[ "a", "b" ]' resize="true"
                  labels='[ "Serie A", "Serie B" ]' line-colors='[ "#FF6384", "#36A2EB" ]'
                  grid="true" grid-text-weight="bold">
                </line-chart>
              </div>
              <div v-else>No Data</div>
            </div>
            <div class="col-sm-6">
              <pre style="border:none; background-color:white">
                <code class="xml">
  &lt;line-chart 
    id="line"
    :data="lineData"
    xkey="year"
    ykeys='[ "a", "b" ]'
    line-colors='[ "#FF6384", "#36A2EB" ]' 
    grid="true"
    grid-text-weight="bold"
    resize="true"&gt;
  &lt;/line-chart&gt;
                </code>
              </pre>
            </div>
          </div>
        </div>

        <div class="col-xs-12 panel panel-default">
          <div class="panel-body">
            <div class="col-sm-6">
              <h3>Donut Chart</h3>
              <donut-chart id="donut" :data="donutData" colors='[ "#FF6384", "#36A2EB", "#FFCE56" ]' resize="true"></donut-chart>
            </div>
            <div class="col-sm-6">
              <pre style="border:none; background-color:white">
                <code class="xml">
  &lt;donut-chart 
    id="donut" 
    :data="donutData" 
    colors='[ "#FF6384", "#36A2EB", "#FFCE56" ]' 
    resize="true"&gt;
  &lt;/donut-chart&gt;

  &lt;script&gt;
  new Vue({
    data: {
      donutData: [
        { label: 'Red', value: 300 },
        { label: 'Blue', value: 50 },
        { label: 'Yellow', value: 100 }
      ]
    },
    components: { DonutChart }
  })
  &lt;/script&gt;
                </code>
              </pre>
            </div>
          </div>
        </div>

        <div class="col-xs-12 panel panel-default">
          <div class="panel-body">
            <div class="col-sm-6">
              <h3>Area Chart</h3>
              <area-chart 
                id="area" :data="areaData" xkey="year" ykeys='[ "a", "b" ]' resize="true"
                labels='[ "Serie A", "Serie B" ]' line-colors='[ "#FF6384", "#36A2EB" ]'
                grid="true" grid-text-weight="bold" hide-hover="always">
              </area-chart>
            </div>
            <div class="col-sm-6">
              <pre style="border:none; background-color:white">
                <code class="xml">
  &lt;area-chart 
    id="area"
    data='[
        { year: "2013", a: 30, b: 5 },
        { year: "2014", a: 25, b: 15 },
        { year: "2015", a: 29, b: 25 },
        { year: "2016", a: 50, b: 20 },
      ]'
    xkey="year"
    ykeys='[ "a", "b" ]'
    labels='[ "Serie A", "Serie B" ]'
    line-colors='[ "#FF6384", "#36A2EB" ]' 
    grid="true"
    grid-text-weight="bold"
    resize="true"
    hide-hover="always"&gt;
  &lt;/area-chart&gt;
                </code>
              </pre>
            </div>
          </div>
        </div>

        <div class="col-xs-12 panel panel-default">
          <div class="panel-body">
            <div class="col-sm-6">
              <h3>Area Chart <small>Example with the default value for xkey, ykeys and labels</small></h3>
              <area-chart 
                id="area_2" data='[
                  { "key": "2013", "value": 30 },
                  { "key": "2014", "value": 25 },
                  { "key": "2015", "value": 29 },
                  { "key": "2016", "value": 50 }
                ]'
                resize="true" line-colors='[ "#FF6384", "#36A2EB" ]'
                grid="true" grid-text-weight="bold">
              </area-chart>
            </div>
            <div class="col-sm-6">
              <pre style="border:none; background-color:white">
                <code class="xml">
  &lt;area-chart 
    id="area"
    data='[
        { key: "2013", value: 30 },
        { key: "2014", value: 25 },
        { key: "2015", value: 29 },
        { key: "2016", value: 50 }
      ]'
    line-colors='[ "#FF6384", "#36A2EB" ]' 
    grid="true"
    grid-text-weight="bold"
    resize="true"&gt;
  &lt;/area-chart&gt;
                </code>
              </pre>
            </div>
          </div>
        </div>
    
      </div>
    </div>
  </div>
</template>

<script>
import Raphael from 'raphael/raphael'
global.Raphael = Raphael
import { DonutChart, BarChart, LineChart, AreaChart } from 'vue-morris'

export default {
  name: 'app',

  data () {
    return {
      donutData: [
        { label: 'Red', value: 300 },
        { label: 'Blue', value: 50 },
        { label: 'Yellow', value: 100 }
      ],

      barData: [
        { year: '2013', and: 10, ios: 5, win: 2 },
        { year: '2014', and: 10, ios: 15, win: 3 },
        { year: '2015', and: 20, ios: 25, win: 2 },
        { year: '2016', and: 30, ios: 20, win: 1 },
      ],

      lineData: [],/*[
        { year: '2013', a: 10, b: 5 },
        { year: '2014', a: 40, b: 15 },
        { year: '2015', a: 20, b: 25 },
        { year: '2016', a: 30, b: 20 },
      ],*/

      areaData: [
        { year: '2013', a: 30, b: 5 },
        { year: '2014', a: 25, b: 15 },
        { year: '2015', a: 29, b: 25 },
        { year: '2016', a: 50, b: 20 },
      ]
    }
  },

  components: {
    DonutChart, BarChart, LineChart, AreaChart
  },

  mounted () {
    setInterval(() => {
      this.lineData = [
        { year: '2013', a: this.rand(100), b: this.rand(100) },
        { year: '2014', a: this.rand(100), b: this.rand(100) },
        { year: '2015', a: this.rand(100), b: this.rand(100) },
        { year: '2016', a: this.rand(100), b: this.rand(100) },
      ]
    }, 5000)
  },

  methods: {
    rand (limit) {
      return Math.round(Math.random() * limit)
    }
  }

}
</script>
