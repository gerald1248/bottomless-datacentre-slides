---
title: Continuous Documentation
pdf: continuous-documentation.pdf
slideNumber: true
controls: false
transition: slide
backgroundTransition: fade
asciinema: true
---

# THE BOTTOMLESS DATACENTRE {bgcss=tw-colorful .light-on-dark}

```render_a2sketch
.-----------------------------------.    
|[c]                                |    
|    sustainable cloud computing    |
|                                   |
'-----------------------------------'    

[c]: {"a2s:type": "cloud", "a2s:delref": true, "fill": "#fff", "fillStyle": "solid"}

```

# BOA CONSTRICTOR {bgcss=tw-bg-yellow}

```render_vegalite
{
    "$schema": "https://vega.github.io/schema/vega-lite/v2.0.json",
    "data": {
        "values": [
            {"Y": 22, "X": 0},
            {"Y": 21, "X": 1},
            {"Y": 20, "X": 2},
            {"Y": 20, "X": 3},
            {"Y": 20, "X": 4},
            {"Y": 18, "X": 5},
            {"Y": 21, "X": 6},
            {"Y": 18, "X": 7},
            {"Y": 17, "X": 8},
            {"Y": 15, "X": 9},
            {"Y": 12, "X": 10},
            {"Y": 12, "X": 11},
            {"Y": 12, "X": 12},
            {"Y": 10, "X": 13},
            {"Y": 0, "X": 14}
        ]
    },
    "width": 400,
    "height": 200,
    "mark": { "type": "line", "color": "#ef5ba1" },
    "encoding": {
        "x": { "field": "X", "type": "quantitative", "scale": {"domain": [0,14]}},
        "y": {"field": "Y", "type": "quantitative", "scale": {"domain": [0, 22]}}
    },
    "config": {
        "axis": {
            "labelFont": "sans-serif",
            "labelFontSize": 18,
            "titleFont": "sans-serif",
            "titleFontSize": 24,
            "titleAngle": 0
        },
        "axisX": {
            "labelAngle": 0
        }
    }
}
```

# THE MATRIX {bgcss=tw-bg-yellow}

```render_a2sketch
no need to ask ^
               |
               |                     .-------.       
               |                     |• Docs |
               |                     '-------'     
               |                      
               |                      
               |
               |                      
               |                            • Pairing
               |                        
               |
               |
               |
               |                                        • Training
               |
               |
               |
               '--------------------------------------------------->
                                   we're serious about handing over

```

# WORKFLOW {bgcss=tw-bg-yellow}

```render_a2sketch
#--------------------.           #---------------------.
|[b]                 |           |                     |
| Git                |   Push    | Docker build        |
|                    +---------->+                     |
|                    |           |                     |
|                    |           |                     |
'--------------------#           '----------+----------#
                                            ^           
                                            | watch    
                                 #----------+----------.
                                 |                     |
                                 | Flux                |
                                 |                     |
                                 |                     |
                                 |                     |
                                 '----------+----------#
                                            |          
                                            v trigger  
                                 #----------+----------.            #-----------------.    
                                 |                     |            |[p]              |
                                 | Helm                | deploy     | Service         |
                                 |                     +----------->+                 |
                                 |                     |            |                 |
                                 |                     |            |                 |
                                 '---------------------#            '-----------------#
[b]: {"fill": "#ef5ba1", "a2s:delref": true, "fillStyle": "solid"}
[p]: {"fill": "#27bdce", "a2s:delref": true, "fillStyle": "solid"}
```

# MINIMAL WORKFLOW {bgcss=tw-bg-yellow}

```render_a2sketch
#--------------------.           #---------------------.            #-----------------.    
|[p]                 |           |                     |            |[s]              |
| Make               |   build   | HTML                |            | PDF             |
|                    +---------->+                     +------------+                 |
|                    |           |                     |            |                 |
|                    |           |                     |            |                 |
'--------------------#           '----------+----------#            '-----------------#
                                            |           
                                            v update    
                                 #----------+----------.
                                 |                     |
                                 | ConfigMap           |
                                 |                     |
                                 |                     |
                                 |                     |
                                 '----------+----------#
                                            |          
                                            v replace
                                 #----------+----------.
                                 |[b]                  |
                                 | Pod                 |
                                 |                     |
                                 |                     |
                                 |                     |
                                 '---------------------#

[s]: {"a2s:type": "document", "a2s:delref": true}
[b]: {"fill": "#27bdce", "a2s:delref": true, "fillStyle": "solid"}
[p]: {"fill": "#ef5ba1", "a2s:delref": true, "fillStyle": "solid"}
```

# SHOESTRING CI {bgcss=tw-bg-purple .light-on-dark}

```dockerfile
FROM gerald1248/asciidoctor:latest as builder
ADD . /documents/
RUN ./test_builder.sh
RUN ./render.sh
RUN ./test_output.sh

FROM centos/httpd-24-centos7:latest
COPY --from=builder /documents/output /var/www/html
```

# ON AND ON

# AND ON