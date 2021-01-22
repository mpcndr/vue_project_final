<template>
  <div>
    <div id="mySubcal" style="width: 100vw; height: 90vh"></div>
  </div>
</template>

<script>
import go from "gojs";
export default {
  name: "subject_cal",
  props: {},
  data() {
    return {
      nodeSubject: [
        { key: 1, text: "Alpha" },
        { key: 2, text: "GROUP", isGroup: true },
        { key: 3, text: "Beta", group: 2 },
        { key: 4, text: "Gamma", group: 2 },
        { key: 5, text: "Delta" },
        // {
        //   key: 0,
        //   text: "คำนวณหลักสูตร",
        //   isGroup: true,
        // },
        // {
        //   key: 1.1,
        //   text: "1 term 1",
        //   isGroup: true,
        //   group: 0,
        //   color: "#000",
        // },
        // {
        //   key: 11,
        //   items: [
        //     { text: "english for everyday use", grade: "1" },
        //     { text: "health edu in the elementary school", grade: "1" },
        //     { text: "precalculus", grade: "1" },
        //     { text: "calculus for com sci 1", grade: "1" },
        //     { text: "fundamental physics", grade: "1" },
        //     { text: "com programming skill 1", grade: "1" },
        //     { text: "foundation of com and infor", grade: "1" },
        //   ],
        //   group: 1.1,
        // },
        // {
        //   key: 12,
        //   items: [
        //     { text: "english skills development", grade: "1" },
        //     { text: "sport edu", grade: "1" },
        //     { text: "earth&astronomy", grade: "1" },
        //     { text: "creative su", grade: "1" },
        //     { text: "calculus for com sci 2", grade: "1" },
        //     { text: "elementary statistics", grade: "1" },
        //     { text: "com programming skill 2", grade: "-1" },
        //   ],
        // },
        // {
        //   key: 13,
        //   items: [{ text: "com programming skill 2", grade: "1" }],
        // },
        // {
        //   key: 21,
        //   items: [
        //     { text: "recreation program in elementary school", grade: "1" },
        //     { text: "scientific eng", grade: "1" },
        //     { text: "probability for com sci", grade: "1" },
        //     { text: "data structures", grade: "-1" },
        //     { text: "digital logic design", grade: "1" },
        //     { text: "discrete computational structures", grade: "-1" },
        //     {
        //       text: "programming statistical learning for big data",
        //       grade: "1",
        //     },
        //   ],
        // },
        // {
        //   key: 22,
        //   items: [
        //     { text: "communicative eng", grade: "1" },
        //     { text: "data structures", grade: "1" },
        //     { text: "com organization&architecture", grade: "1" },
        //     { text: "data communications&com networks", grade: "1" },
        //     { text: "database systems", grade: "1" },
        //   ],
        // },
        // {
        //   key: 31,
        //   items: [
        //     { text: "thai for communication", grade: "1" },
        //     { text: "discrete computational structures", grade: "1" },
        //     { text: "algorithm analysis&design", grade: "1" },
        //     { text: "operating systems", grade: "1" },
        //     { text: "mobile application dev", grade: "1" },
        //     { text: "laws&ethics in infor technology", grade: "1" },
        //     { text: "system analysis&design", grade: "1" },
        //   ],
        // },
        // {
        //   key: 32,
        //   items: [
        //     { text: "linear algebra with applications", grade: "1" },
        //     { text: "oblect-oriented software dev", grade: "1" },
        //     { text: "theory of computation", grade: "1" },
        //     { text: "research methods", grade: "1" },
        //     { text: "selected topics in com sci VI", grade: "1" },
        //     { text: "white internet", grade: "1" },
        //     { text: "software engineering", grade: "1" },
        //     { text: "infomation storage&retrieval", grade: "1" },
        //   ],
        // },
        // {
        //   key: 41,
        //   items: [
        //     { text: "com programming skill 2", grade: "1" },
        //     { text: "principles of programming languages", grade: "1" },
        //     {
        //       text: "internet&world wide web technology&progamming",
        //       grade: "1",
        //     },
        //     { text: "innovative startup entrepreneurship for sci", grade: "1" },
        //   ],
        // },
        // {
        //   key: 42,
        //   items: [
        //     { text: "electives", grade: "0" },
        //     { text: "research project 1", grade: "0" },
        //     { text: "human com interaction&interface design", grade: "0" },
        //   ],
        // },
        // {
        //   key: 43,
        //   items: [{ text: "research project 2", grade: "0" }],
        // },
      ],
      subjects: [],
      
    };
  },
  methods: {
    Diagram: function() {
      var $ = go.GraphObject.make;
      var myDiagram = $(go.Diagram, "mySubcal", {
        initialContentAlignment: go.Spot.Center,
      });

      myDiagram.groupTemplate = $(
        go.Group,
        "Auto",
        $(go.Shape, "Rectangle", { fill: "gold" }),
        $(
          go.Panel,
          "Vertical",
          { margin: 5, defaultAlignment: go.Spot.Left },
          $(
            go.Panel,
            "Horizontal",
            $("SubGraphExpanderButton", { margin: new go.Margin(0, 3, 5, 0) }),
            $(go.TextBlock, "Group")
          ),
          $(go.Placeholder)
        )
      );
      myDiagram.model = new go.GraphLinksModel(
        this.nodeSubject
      );
    },
  },
  mounted: function() {
    this.Diagram();
  },
};
</script>

<style scoped>
.title {
  padding-top: 20%;
}
</style>
