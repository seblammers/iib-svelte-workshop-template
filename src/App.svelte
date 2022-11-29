<script>
  import data from "./data/data.json";
  console.log(data);

  import { scaleLinear, scaleTime } from "d3-scale";

  let height = 400;

  const yScale = scaleLinear()
    .domain([0, 100]) // INPUT
    .range([height, 0]); // OUTPUT

  let width = 400;

  let minDate = new Date("2020/06/01");
  let maxDate = new Date("2020/11/03");
  const xScale = scaleTime()
    .domain([minDate, maxDate]) // INPUT
    .range([0, width]); // OUTPUT

  import Line from "./lib/Line.svelte";
</script>

<svg {width} {height}>
  <Line {xScale} {yScale} data={data.Biden} color="blue" />
  <Line {xScale} {yScale} data={data.Trump} color="red" />
</svg>