<template>
  <div>
    <svg ref="svgCanvas" width="1000" height="500"></svg>
  </div>
</template>

<script>
import * as d3 from 'd3';

export default {
  name: 'D3Shapes',
  mounted() {
    const svg = d3.select(this.$refs.svgCanvas);

    this.group1 = svg.append("g")
        .attr("class", "movable-group1");

    this.group2 = svg.append("g")
        .attr("class", "movable-group2");

    svg.append("circle")
        .attr("cx", 100)  // Координата X центра
        .attr("cy", 100)  // Координата Y центра
        .attr("r", 50)    // Радиус круга
        .attr("stroke", "black")  // Цвет круга
        .attr("fill", "white");  // Цвет круга

    svg.append("circle")
        .attr("cx", 450)  // Координата X центра
        .attr("cy", 100)  // Координата Y центра
        .attr("r", 50)    // Радиус круга
        .attr("stroke", "black")  // Цвет круга
        .attr("fill", "white");  // Цвет круга

    // Рисуем стрелку
    this.group1.append("line")
        .attr("x1", 50)  // Координата X начала линии
        .attr("y1", 250)  // Координата Y начала линии
        .attr("x2", 250)  // Координата X конца линии
        .attr("y2", 250)  // Координата Y конца линии
        .attr("stroke", "black")  // Цвет линии
        .attr("stroke-width", 1); // Толщина линии

    this.group1.append("polygon")
        .attr("points", "250,240 270,250 250,260")
        .attr("fill", "black");  // Цвет наконечника

    // Рисуем стрелку
    this.group2.append("line")
        .attr("x1", 250)  // Координата X начала линии
        .attr("y1", 250)  // Координата Y начала линии
        .attr("x2", 50)   // Координата X конца линии
        .attr("y2", 250)  // Координата Y конца линии
        .attr("stroke", "black")  // Цвет линии
        .attr("stroke-width", 1); // Толщина линии

    this.group2.append("polygon")
        .attr("points", "50,240 30,250 50,260")
        .attr("fill", "black");  // Цвет наконечника

  }


};
</script>

<style>
.movable-group1 {
  transform: translate(120px, -130px);
}

.movable-group2 {
  transform: translate(140px, -160px);
}
</style>
