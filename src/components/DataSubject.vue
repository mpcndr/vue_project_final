<template>
  <div>
    <div style="width: 100vw; height:8vh"></div>
    <div id="myDiagramDiv" style="width: 100vw; height:62vh;"></div>
    <div id="myAsignatura" style="width: 100vw; height:29.5vh;"></div>
  </div>
</template>

<script>
import go from "gojs";
export default {
  name: "diagram_dataSubject",

  data: function() {
    return {
      nodeDataArray: [
        {
          key: 11,
          text: "1 Term 1",
          isGroup: true,
        },
        {
          key: 12,
          text: "1 Term 2",
          isGroup: true,
        },
        {
          key: 21,
          text: "2 Term 1",
          isGroup: true,
        },
        {
          key: 22,
          text: "2 Term 2",
          isGroup: true,
        },
        {
          key: 31,
          text: "3 Term 1",
          isGroup: true,
        },
        {
          key: 32,
          text: "3 Term 2",
          isGroup: true,
        },
        {
          key: 41,
          text: "4 Term 1",
          isGroup: true,
        },
        {
          key: 42,
          text: "4 Term 2",
          isGroup: true,
        },
        /*------1 term 1 ------*/
        {
          key: "511100",
          name: "Precal",
          group: 11,
          color: "#f08a5d",
        },
        {
          key: "511108",
          name: "Cal I",
          group: 11,
          color: "#f08a5d",
        },
        {
          key: "081102",
          name: "English I",
          group: 11,
          color: "#E74C3C",
        },
        {
          key: "514107",
          name: "Physic",
          group: 11,
          color: "#838383",
        },
        {
          key: "517121",
          name: "Com I",
          group: 11,
          color: "#0d7377",
        },
        {
          key: "520101",
          name: "ComFound",
          group: 11,
          color: "#b83b5e",
        },
        /*------1 term 2 ------*/
        {
          key: "081103",
          name: "English II",
          group: 12,
          color: "#E74C3C",
        },
        {
          key: "511109",
          name: "Cal II",
          group: 12,
          color: "#f08a5d",
        },
        {
          key: "515201",
          name: "Static",
          group: 12,
          color: "darkorange",
        },
        {
          key: "517122",
          name: "Com II",
          group: 12,
          color: "#0d7377",
        },
        {
          key: "01",
          name: "วิชาบังคับเลือกในหมวดศึกษาทั่วไป",
          group: 12,
          color: "darkorange",
        },
        /*------2 term 1 ------*/
        {
          key: "510201",
          name: "English for Science",
          group: 21,
          color: "green",
        },
        {
          key: "515232",
          name: "Prop",
          group: 21,
          color: "darkorange",
        },
        {
          key: "517211",
          name: "Data Struce",
          group: 21,
          color: "#0d7377",
        },
        {
          key: "517212",
          name: "Digital",
          group: 21,
          color: "#0d7377",
        },
        {
          key: "520213",
          name: "Discreat",
          group: 21,
          color: "#b83b5e",
        },
        {
          key: "520215",
          name: "Big Data",
          group: 21,
          color: "#b83b5e",
        },
        /*------2 term 2 ------*/
        {
          key: "510202",
          name: "English",
          group: 22,
          color: "purple",
        },
        {
          key: "511242",
          name: "Linear",
          group: 22,
          color: "#f08a5d",
        },
        {
          key: "517221",
          name: "OOSD",
          group: 22,
          color: "#0d7377",
        },
        {
          key: "517222",
          name: "ComOrganiz",
          group: 22,
          color: "#0d7377",
        },
        {
          key: "520221",
          name: "DataBase",
          group: 22,
          color: "#b83b5e",
        },
        {
          key: "517241",
          name: "DataCom",
          group: 22,
          color: "#0d7377",
        },
        /*------3 term 1 ------*/
        {
          key: "081101",
          name: "Thai",
          group: 31,
          color: "#E74C3C",
        },
        {
          key: "517311",
          name: "Algorithm",
          group: 31,
          color: "#0d7377",
        },
        {
          key: "517312",
          name: "OS",
          group: 31,
          color: "#0d7377",
        },
        {
          key: "517321",
          name: "PL",
          group: 31,
          color: "#0d7377",
        },
        {
          key: "520212",
          name: "Laws",
          group: 31,
          color: "#b83b5e",
        },
        {
          key: "520361",
          name: "SA",
          group: 31,
          color: "#b83b5e",
        },
        {
          key: "02",
          name: "วิชาเลือกในหมวดวิชาเฉพาะ",
          group: 31,
          color: "purple",
        },
        /*------3 term 2 ------*/
        {
          key: "517313",
          name: "Theory",
          group: 32,
          color: "#0d7377",
        },
        {
          key: "517391",
          name: "RM",
          group: 32,
          color: "#0d7377",
        },
        {
          key: "520351",
          name: "HCI",
          group: 32,
          color: "#b83b5e",
        },
        {
          key: "520362",
          name: "SE",
          group: 32,
          color: "#b83b5e",
        },
        {
          key: "02",
          name: "วิชาเลือกในหมวดวิชาเฉพาะ",
          group: 32,
          color: "purple",
        },
        {
          key: "03",
          name: "วิชาเลือกในรายวิชาศึกษาทั่วไปที่กําหนดโดยคณะวิทยาศาสตร์",
          group: 32,
          color: "purple",
        },
        /*------4 term 1 ------*/
        {
          key: "517493",
          name: "Project I",
          group: 41,
          color: "#0d7377",
        },
        {
          key: "02",
          name: "วิชาเลือกในหมวดวิชาเฉพาะ",
          group: 41,
          color: "purple",
        },
        {
          key: "01",
          name: "วิชาบังคับเลือกในหมวดวิชาศึกษาทั่วไป",
          group: 41,
          color: "purple",
        },
        {
          key: "04",
          name: "วิชาเลือกในหมวดวิชาเลือกเสรี",
          group: 41,
          color: "purple",
        },
        /*------4 term 2 ------*/
        {
          key: "517494",
          name: "Project II",
          group: 42,
          color: "#0d7377",
        },
        {
          key: "04",
          name: "วิชาเลือกในหมวดวิชาเลือกเสรี",
          group: 42,
          color: "purple",
        },
      ],
      linkDataArray: [
        { from: "511100", to: "511108" },
        { from: "517121", to: "517122" },
        { from: "517121", to: "517222" },
        { from: "520101", to: "517212" },
        { from: "081102", to: "081103" },
        { from: "511108", to: "511109" },
        { from: "511108", to: "511242" },
        { from: "511109", to: "520213" },
        { from: "511109", to: "515232" },
        { from: "517122", to: "517211" },
        { from: "517122", to: "520215" },
        { from: "517122", to: "517241" },
        { from: "081103", to: "510201" },
        { from: "517213", to: "517311" },
        { from: "517213", to: "517313" },
        { from: "517211", to: "517221" },
        { from: "517211", to: "520221" },
        { from: "517211", to: "517311" },
        { from: "517212", to: "517222" },
        { from: "510201", to: "510202" },
        { from: "517221", to: "517321" },
        { from: "520221", to: "520361" },
        { from: "517222", to: "517312" },
        { from: "520361", to: "520362" },
      ],
    };
  },
  methods: {
    getUnits: function() {
      var $ = go.GraphObject.make;

      var myDiagram = $(go.Diagram, "myDiagramDiv", {
        initialAutoScale: go.Diagram.UniformToFill,
        //maxScale: 0.5,
        initialContentAlignment: go.Spot.Center,
        isReadOnly: false,
        "animationManager.isEnabled": false,
        "undoManager.isEnabled": true,
        layout: $(go.TreeLayout, {
          angle: 0,
          //sorting: go.TreeLayout.SortingAscending,
          layerSpacing: 40,
          nodeSpacing: 20,
          layerStyle: go.TreeLayout.LayerUniform,
          treeStyle: go.TreeLayout.StyleLayered,
        }),
        maxSelectionCount: 1,
        ChangedSelection: showLocalOnFullClick,
      });

      var myAsignatura = $(go.Diagram, "myAsignatura", {
        initialAutoScale: go.Diagram.UniformToFill,
        initialContentAlignment: go.Spot.Center,
        isReadOnly: true,
        layout: $(go.TreeLayout, {
          angle: 0,
          //sorting: go.TreeLayout.SortingAscending
          layerSpacing: 40,
          nodeSpacing: 20,
          layerStyle: go.TreeLayout.LayerUniform,
          //treeStyle: go.TreeLayout.StyleLayered,
          //alignment: go.TreeLayout.AlignmentEnd,
          //arrangement: go.TreeLayout.ArrangementVertical,
          //sorting: go.TreeLayout.SortingAscending
        }),
        LayoutCompleted: function(e) {
          var sel = e.diagram.selection.first();
          if (sel !== null) myAsignatura.scrollToRect(sel.actualBounds);
        },
        maxSelectionCount: 1,
        ChangedSelection: showLocalOnLocalClick,
      });

      var highlighter = $(
        go.Part,
        "Auto",
        {
          layerName: "Background",
          selectable: false,
          //isInDocumentBounds: false,
          locationSpot: go.Spot.Center,
        },
        $(go.Shape, "Ellipse", {
          fill: "white",
          stroke: "lightgrey",
          strokeWidth: 4,
        })
      );

      myDiagram.model = new go.GraphLinksModel(
        this.nodeDataArray,
        this.linkDataArray
      );

      myDiagram.undoManager.isEnabled = true;

      myDiagram.add(
        $(
          go.Part,
          $(go.TextBlock, "Carrera", {
            margin: 10,
            font: "32px Kanit",
            stroke: "white",
            isMultiline: false,
            //editable: true
          })
        )
      );

      myDiagram.isReadOnly = true;

      myDiagram.groupTemplate = $(
        go.Group,
        "Auto",
        {
          layout: $(go.LayeredDigraphLayout, {
            direction: 0,
            columnSpacing: 10,
          }),
        },
        $(go.Shape, "Rectangle", { fill: "#fff9f1", stroke: "#000" }),
        $(
          go.Panel,
          "Table",
          { margin: 2 },
          $(go.RowColumnDefinition, { row: 0, background: "white" }),
          $("SubGraphExpanderButton", { row: 0, column: 0, margin: 5 }),
          $(
            go.TextBlock,
            {
              row: 0,
              column: 1,
              font: "14px Kanit",
              stroke: "darkorange",
              textAlign: "center",
              stretch: go.GraphObject.Horizontal,
            },
            new go.Binding("text")
          ),
          $(
            go.Placeholder,
            { row: 1, columnSpan: 2, padding: 5, alignment: go.Spot.TopLeft },
            new go.Binding("padding", "isSubGraphExpanded", function(exp) {
              return exp ? 2 : 0;
            }).ofObject()
          )
        )
      );

      myDiagram.layout = $(go.TreeLayout, { isRealtime: true });

      myDiagram.nodeTemplate = $(
        go.Node,
        "Auto",
        {
          desiredSize: new go.Size(100, 40),
          fromSpot: go.Spot.Right,
          toSpot: go.Spot.Left,
        } /*new go.Binding("location", "loc", go.Point.parse),*/,
        $(
          go.Shape,
          "RoundedRectangle",
          { strokeWidth: 0 },
          new go.Binding("fill", "color")
        ),
        $(
          go.TextBlock,
          { margin: 5 },
          new go.Binding("stroke", "color", function(c) {
            return go.Brush.isDark(c) ? "white" : "black";
          }),
          new go.Binding("text", "key")
        )
      );
      myDiagram.linkTemplate = $(
        go.Link,
        { routing: go.Link.Orthogonal, corner: 10, curve: go.Link.JumpOver },
        $(go.Shape),
        $(go.Shape, { toArrow: "Standard" })
      );

      var myNodeTemplate = $(
        go.Node,
        "Auto",
        {
          locationSpot: go.Spot.Center,
          click: function(e, node) {
            var diagram = node.diagram;
            diagram.startTransaction("highlight");
            diagram.clearHighlighteds();
            node.findLinksConnected().each(function(l) {
              l.isHighlighted = true;
            });
            node.findNodesConnected().each(function(n) {
              n.isHighlighted = true;
            });
            /*node.findNodesOutOf().each(function(n) {
        n.isHighlighted = true;
      });
      node.findLinksOutOf().each(function(l) {
        l.isHighlighted = true;
      });*/
            diagram.commitTransaction("highlight");
          },
        },
        new go.Binding("text", "key", go.Binding.toString),
        $(
          go.Shape,
          "RoundedRectangle",
          new go.Binding("fill", "color"),
          new go.Binding("stroke", "isHighlighted", function(h) {
            return h ? "black" : "grey";
          }).ofObject(),
          //new go.Binding("strokeWidth", "isHighlighted", function(h) { return h ? 2 : 2; }).ofObject(),
          {
            stroke: "grey",
            strokeWidth: 0,
          }
        ),
        {
          selectionAdornmentTemplate: $(
            go.Adornment,
            "Auto",
            $(
              go.Shape,
              "RoundedRectangle",
              {
                fill: null,
                stroke: "black" /*dimgrey,dodgerblue*/,
                strokeWidth: 2,
              }
              //new go.Binding("stroke", "color")
            ),
            $(go.Placeholder, { padding: -4 })
          ),
        },
        $(
          go.TextBlock,
          "Default Text",
          {
            margin: 4,
            font: "14px Kanit",
            stroke: "white",
            isMultiline: false,
            //editable: true
          },
          new go.Binding("text", "name").makeTwoWay()
        )
      );

      myDiagram.nodeTemplate = myNodeTemplate;
      myAsignatura.nodeTemplate = myNodeTemplate;

      var myLinkTemplate = $(
        go.Link,
        {
          click: function(e, link) {
            const diagram = link.diagram;
            diagram.startTransaction("highlight");
            diagram.clearHighlighteds();
            link.isHighlighted = true;
            link.fromNode.isHighlighted = true;
            link.toNode.isHighlighted = true;
            diagram.commitTransaction("highlight");
          },
          routing: go.Link.AvoidsNodes /*Normal*/,
          selectable: true,
          corner: 10,
          //relinkableFrom: true,
          //relinkableTo: true,
          curve: go.Link.JumpGap,
        },
        $(
          go.Shape,
          new go.Binding("stroke", "isHighlighted", function(h) {
            return h ? "black" : "grey";
          }).ofObject(),
          new go.Binding("strokeWidth", "isHighlighted", function(h) {
            return h ? 4 : 2;
          }).ofObject(),
          //{ stroke: "silver", strokeWidth: 2 }
          new go.Binding("strokeDashArray", "isHighlighted", function(h) {
            return h ? [10, 6] : [0, 0];
          }).ofObject(),
          { name: "PIPE", strokeCap: "round" }
        ),
        $(
          go.Shape,
          {
            toArrow:
              "Triangle" /*Standard,Boomerang,Block,Circle,Diamond,Fork*/,
            //fill: "grey",
            //stroke: "grey",
            strokeWidth: 2,
          },
          new go.Binding("fill", "isHighlighted", function(h) {
            return h ? "black" : "grey";
          }).ofObject(),
          new go.Binding("stroke", "isHighlighted", function(h) {
            return h ? "black" : "grey";
          }).ofObject(),
          new go.Binding("strokeWidth", "isHighlighted", function(h) {
            return h ? 4 : 2;
          }).ofObject()
        ),
        {
          selectionAdornmentTemplate: $(go.Adornment, "Auto"),
        }
      );
      myDiagram.linkTemplate = myLinkTemplate;
      myAsignatura.linkTemplate = myLinkTemplate;

      highlighter = $(
        go.Part,
        "Auto",
        {
          layerName: "Background",
          selectable: false,
          //isInDocumentBounds: false,
          locationSpot: go.Spot.Center,
        },
        $(go.Shape, "Ellipse", {
          fill: "white",
          stroke: "lightgrey",
          strokeWidth: 4,
        })
      );
      myDiagram.add(highlighter);
      myDiagram.addDiagramListener("InitialLayoutCompleted", function() {
        var node0 = myDiagram.findPartForKey(0);
        if (node0 !== null) node0.isSelected = true;
        showLocalOnFullClick();
      });

      function showLocalOnFullClick() {
        var node = myDiagram.selection.first();
        if (node !== null && node instanceof go.Node) {
          //highlighter.visible = true;
          myDiagram.scrollToRect(node.actualBounds);
          highlighter.location = node.location;

          var model = new go.GraphLinksModel();
          var nearby = node.findTreeParts(2);
          //var parent = node.findTreeParentNode();
          var links = node.findLinksConnected();
          var nodes = node.findNodesInto();
          //nearby.add(nodes);

          nearby.each(function(n) {
            if (n instanceof go.Node) model.addNodeData(n.data);
            //model.addLinkData(n.data);
          });

          links.each(function(l) {
            model.addLinkData(l.data);
          });
          nodes.each(function(n) {
            model.addNodeData(n.data);
          });

          myAsignatura.model = model;
          var selectedLocal = myAsignatura.findPartForKey(node.data.key);
          if (selectedLocal !== null) selectedLocal.isSelected = true;
        } else {
          //asignatura.clearSelection();
          highlighter.visible = false;
          myAsignatura.clear();
        }
      }
      myDiagram.click = function() {
        myDiagram.startTransaction("no highlighteds");
        myDiagram.clearHighlighteds();
        myDiagram.commitTransaction("no highlighteds");
      };
      function showLocalOnLocalClick() {
        var selectedLocal = myAsignatura.selection.first();
        if (selectedLocal !== null) {
          myDiagram.select(myDiagram.findPartForKey(selectedLocal.data.key));
        }
      }

      // function loop() {
      //   var diagram = myDiagram;
      //   setTimeout(function() {
      //     var oldskips = diagram.skipsUndoManager;
      //     diagram.skipsUndoManager = true;
      //     diagram.links.each(function(link) {
      //       var shape = link.findObject("PIPE");
      //       var off = shape.strokeDashOffset - 1;
      //       shape.strokeDashOffset = off <= 0 ? 16 : off;
      //     });
      //     diagram.skipsUndoManager = oldskips;
      //     loop();
      //   }, 50);
      // }
      // function setupDiagram(total) {
      //   if (total === undefined) total = 20;
      //   var nodeDataArray = [];
      //   for (var i = 0; i < total; i++) {
      //     nodeDataArray.push({
      //       key: nodeDataArray.length,
      //       color: go.Brush.randomColor(),
      //     });
      //   }
      //   var j = 0;
      //   for (let i = 1; i < total; i++) {
      //     var data = nodeDataArray[i];
      //     data.parent = j;
      //     if (Math.random() < 0.3) j++;
      //   }
      //   myDiagram.model = new go.TreeModel(nodeDataArray);
      // }
    },
  },
  mounted: function() {
    this.getUnits();
  },
};
</script>

<style scoped>
/* body {
  background: darkgrey;
}
.diagram {
  height: 240px;
  width: 100%;
  border: 1px solid lightgrey;
}
.topDiagram {
  margin-top: 10px;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
  border-bottom: none;
}
.bottomDiagram {
  border-bottom-left-radius: 5px;
  border-bottom-right-radius: 5px;
  margin-bottom: 10px;
}
#carreraDiagram {
  background: lightgrey;
}
#asignaturaDiagram {
  background: whitesmoke;
} */
</style>
