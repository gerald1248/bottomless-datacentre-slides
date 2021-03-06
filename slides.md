---
title: The bottomless datacentre
pdf: bottomless-datacentre.pdf
slideNumber: true
controls: false
transition: slide
backgroundTransition: fade
asciinema: true
center: true
---

<link href="//netdna.bootstrapcdn.com/font-awesome/4.1.0/css/font-awesome.min.css" rel="stylesheet">

# THE BOTTOMLESS DATACENTRE {bgcss=tw-colorful .light-on-dark}

```render_a2sketch
.-----------------------------------.    
|[c]                                |    
|                                   |    
|    sustainable cloud computing    |
|                                   |    
|                                   | 
'-----------------------------------'    

[c]: {"a2s:type": "cloud", "a2s:delref": true, "fill": "#fff", "fillStyle": "solid"}
```

<aside class="notes" data-markdown>
Public cloud vendors are increasing supply so fast it is worth asking how demand manages to keep up. Have existing compute requirements moved from one domain to another, or has it grown very significantly? Is this sustainable?  
</aside>

# NEWSPEAK

```render_a2sketch
.--------------------------------------------------------------.    
|[c]                                                           |    
|                       air                                    |    
|                              gauze                           |
|                                      rounded                 |    
|             fluffy                                           | 
|                          floating                            | 
|                                          ethereal            | 
|                     Wordsworth                               | 
|              soft                                            | 
|                           sunlight                           | 
|                                        Eloi                  | 
|                      silent                                  | 
|          weightless                                          | 
|                                   feathery                   | 
|                 Turner                                       | 
|                                                              | 
'--------------------------------------------------------------'    

[c]: {"a2s:type": "cloud", "a2s:delref": true, "fill": "#fff", "fillStyle": "solid"}

```

<aside class="notes" data-markdown>
The cloud is inspired marketing. Every one of these associations is wholly unsuited to the real-world datacentres that collectively make up the cloud.
</aside>

# GROUNDED {bg=#000 .light-on-dark}

```render_a2sketch
#--------------------------------------------------------------#
|[s]                                                           |
|                 barbed wire                                  |
|                                     cooling fans             |
|      rectangular                                             |
|                               industrial                     |
|                 warehouse                                    |
|                                         Morlocks             |
|                             security                         |
|            rows of racks                                     |
|                                 artificial light             |
|     unsightly                                                |
|                  physical infrastructure                     |
|           box                                                |
|                                 cables                       |
|                metal                                         |
|                                      blinkenlights           |
|                     electric hum                             |
#--------------------------------------------------------------#

[s]: {"a2s:delref": true, "fill": "#000", "fillStyle": "solid", "stroke": "#fff"}

```
<aside class="notes" data-markdown>
Here is a better description of cloud datacentres. Miles of cables pin these fortified data warehouses to the ground. 
</aside>

# COMPUTE-1 AND UP {bg=#fff44d}

```render_vegalite
{
    "$schema": "https://vega.github.io/schema/vega-lite/v2.0.json",
    "data": {
        "values": [
            {"regions": 1, "date": "2006", "symbol": "AMZN" },
            {"regions": 1, "date": "2007", "symbol": "AMZN" },
            {"regions": 2, "date": "2008", "symbol": "AMZN" },
            {"regions": 3, "date": "2009", "symbol": "AMZN" },
            {"regions": 4, "date": "2010", "symbol": "AMZN" },
            {"regions": 8, "date": "2011", "symbol": "AMZN" },
            {"regions": 9, "date": "2012", "symbol": "AMZN" },
            {"regions": 10, "date": "2013", "symbol": "AMZN" },
            {"regions": 11, "date": "2014", "symbol": "AMZN" },
            {"regions": 11, "date": "2015", "symbol": "AMZN" },
            {"regions": 16, "date": "2016", "symbol": "AMZN" },
            {"regions": 16, "date": "2017", "symbol": "AMZN" },
            {"regions": 17, "date": "2018", "symbol": "AMZN" },
            {"regions": 0, "date": "2006", "symbol": "GOOG" },
            {"regions": 0, "date": "2007", "symbol": "GOOG" },
            {"regions": 0, "date": "2008", "symbol": "GOOG" },
            {"regions": 0, "date": "2009", "symbol": "GOOG" },
            {"regions": 0, "date": "2010", "symbol": "GOOG" },
            {"regions": 4, "date": "2011", "symbol": "GOOG" },
            {"regions": 6, "date": "2012", "symbol": "GOOG" },
            {"regions": 8, "date": "2013", "symbol": "GOOG" },
            {"regions": 10, "date": "2014", "symbol": "GOOG" },
            {"regions": 12, "date": "2015", "symbol": "GOOG" },
            {"regions": 14, "date": "2016", "symbol": "GOOG" },
            {"regions": 16, "date": "2017", "symbol": "GOOG" },
            {"regions": 18, "date": "2018", "symbol": "GOOG" },
            {"regions": 0, "date": "2006", "symbol": "MSFT" },
            {"regions": 0, "date": "2007", "symbol": "MSFT" },
            {"regions": 0, "date": "2008", "symbol": "MSFT" },
            {"regions": 0, "date": "2009", "symbol": "MSFT" },
            {"regions": 2, "date": "2010", "symbol": "MSFT" },
            {"regions": 8, "date": "2011", "symbol": "MSFT" },
            {"regions": 14, "date": "2012", "symbol": "MSFT" },
            {"regions": 20, "date": "2013", "symbol": "MSFT" },
            {"regions": 26, "date": "2014", "symbol": "MSFT" },
            {"regions": 32, "date": "2015", "symbol": "MSFT" },
            {"regions": 39, "date": "2016", "symbol": "MSFT" },
            {"regions": 46, "date": "2017", "symbol": "MSFT" },
            {"regions": 54, "date": "2018", "symbol": "MSFT" }
        ]
    },
    "width": 400,
    "height": 200,
    "mark": "bar",
    "encoding": {
        "x": {
            "timeUnit": "year", "field": "date", "type": "temporal"
        },
        "y": {
            "field": "regions", "type": "quantitative", "scale": {"domain": [0, 90]}
        },
        "color": { "field": "symbol", "type": "nominal", "scale": {
          "domain": [ "AMZN", "GOOG", "MSFT" ],
          "range": [ "#fe17bf", "#3364c0", "#27bdce" ]
        } }
    },
    "config": {
        "axis": {
            "labelFont": "sans-serif",
            "labelFontSize": 18,
            "titleFont": "sans-serif",
            "titleFontSize": 18
        },
        "axisX": {
            "labelAngle": 0
        },
        "bar": {
            "continuousBandSize": 20
        }
    }
}
```

<div class="tiny">Region data based on the <a href="http://feeds.feedburner.com/AmazonWebServicesBlog">AWS</a>, <a href="https://cloudblog.withgoogle.com/products/gcp/rss/">GCP</a> and <a href="https://azurecomcdn.azureedge.net/en-gb/blog/feed/">Azure</a> blogs. Some missing data points interpolated.</div>

<aside class="notes" data-markdown>
Note that the growth of AWS is in no way hindered by the rapid rise of Microsoft Azure and Google Compute Cloud. See especially AWS's explosive growth in the period 2015—2016.
</aside>

# INCENTIVES {bg=#97dce7}

$\text{PUE}=\frac{\text{Watts in}}{\text{IT watts}}$

```render_vegalite
{
    "$schema": "https://vega.github.io/schema/vega-lite/v2.0.json",
    "data": {
        "values": [
            {"PUE": 1.21, "date": "2008"},
            {"PUE": 1.19, "date": "2009"},
            {"PUE": 1.18, "date": "2010"},
            {"PUE": 1.14, "date": "2011"},
            {"PUE": 1.13, "date": "2012"},  
            {"PUE": 1.12, "date": "2014"},
            {"PUE": 1.12, "date": "2013"},
            {"PUE": 1.12, "date": "2015"},
            {"PUE": 1.12, "date": "2016"},
            {"PUE": 1.12, "date": "2017"},
            {"PUE": 1.11, "date": "2018"}
        ]
    },
    "width": 400,
    "height": 200,
    "mark": { "type": "line", "color": "#ef5ba1" },
    "encoding": {
        "x": {
            "timeUnit": "year", "field": "date", "type": "temporal"
        },
        "y": {"field": "PUE", "type": "quantitative", "scale": {"domain": [1.1, 1.3]}}
    },
    "config": {
        "axis": {
            "labelFont": "sans-serif",
            "labelFontSize": 18,
            "titleFont": "sans-serif",
            "titleFontSize": 18 
        },
        "axisX": {
            "labelAngle": 0
        }
    }
}
```

<div class="tiny">Power usage effectiveness data by [Google Data Centers](https://www.google.co.uk/about/datacenters/efficiency/internal/).</div>

<aside class="notes" data-markdown>
The power usage effectiveness of these datacentres is nothing short of miraculous, but we mustn't overlook the fact that the actual amount of work done does not come into it. We could be mining Bitcoin at unsustainable financial and environmental cost and still boost a datacentre's PUE indicator. 
</aside>

# INFINITE BEANSTALK

```render_a2sketch
        ^
 utility|   • SETI
        |
        |
        |                                
        |                      .-----------------------.
        |                      |[c]                    |
        |                      |• Elastic Beanstalk app|
        |                      |                       |
        |                      '-----------------------'
        |
        |
        |
        |
        |
        |
        |
        |                                          • Bitcoin
        |
        |    
        #--------------------------------------------------->
                                           power consumption

[c]: {"a2s:delref":true,"a2s:type":"circle"}
```

<aside class="notes">
Now we are able to scale our application with virtually no limit beyond our ability to pay, how do we judge the value of the application we've built?
</aside>

# 1,000,000 SCREENSHOTS

```render_a2sketch
#---------# #---------# #---------# #---------#    
|[c]      | |[c]      | |[c]      | |[c]      |
|         | |         | |         | |         |
|         | |         | |         | |         |
|         | |         | |         | |         |
#---------# #---------# #---------# #---------#

#---------# #---------# #---------# #---------#    
|[c]      | |[c]      | |[cp]     | |[c]      |
|         | |         | |         | |         |
|         | |         | |         | |         |
|         | |         | |         | |         |
#---------# #---------# #---------# #---------#

#---------# #---------# #---------# #---------#    
|[c]      | |[c]      | |[c]      | |[c]      |
|         | |         | |         | |         |
|         | |         | |         | |         |
|         | |         | |         | |         |
#---------# #---------# #---------# #---------#

[c]: {"a2s:type": "computer", "a2s:delref": true, "fill": "#fff", "fillStyle": "solid"}
[cp]: {"a2s:type": "computer", "a2s:delref": true, "fill": "#ef5ba1", "fillStyle": "solid"}

```

<aside class="notes" data-markdown>
Why single out screenshots? Browser UI tests are among the most fragile, but also some of the most resource intensive tests.
</aside>

# PHOENIX CI {bg=#6a2469 .light-on-dark}

<asciinema-player src="./assets/json/build.json" poster="npt:0:0.5" idle-time-limit=2 speed=0.5 rows=18 font-size="medium" />

<aside class="notes" data-markdown>
Process practices such as CI must not be exempt from scrutiny. Isolation and repeatability are laudable goals, but do they justify the absence of caching from much of our build and test activity?
</aside>

# RECIPE {bg=#6a2469 .light-on-dark}

```dockerfile
FROM golang:1.11.1 as builder
WORKDIR /go/src/github.com/gerald1248/k8s-network-policy-viewer/
COPY * ./
RUN go mod download && go get && go vet && go test -v -cover && \
  go build -o k8s-network-policy-viewer .

FROM ubuntu:18.10
WORKDIR /app/
EXPOSE 8080
COPY --from=builder .../k8s-network-policy-viewer /usr/bin/
USER 1000
CMD ["k8s-network-policy-viewer", "-s=true"]
```

<aside class="notes" data-markdown>
Multi-stage docker builds are beguilingly simple and convenient, but harder to justify when run over and over in response to trivial README changes. 
</aside>

# TOTAL COST OF HOARDING

```render_a2sketch

     ^                         
     |#-------------------------------------------.
 cost||[c]                   compute              |
     ||                                           |
     ||                                           |
     ||                                           |
     ||                                           |
     ||                                           |
     ||                                           |
     ||                                           |
     ||                                           |
     ||                                   storage |
     ||                                           |
     ||                                           |
     ||                                           |
     ||                                           |
     ||                                           |
     ||                                           |
     ||                                           |
     ||                                           |
     |#-------------------------------------------#
     #---------------------------------------------->
                                               data

[c]: {"a2s:type": "data", "a2s:delref": true, "fill": "#fff", "fillStyle": "solid"}
```

<aside class="notes" data-markdown>
The cost of data storage scales linearly (allowing for bulk discount tiers), but the complexity of analysing that data grows exponentially. If data is the new oil, it requires each owner to invent their own method of extraction and filtering. 
</aside>

# THE VIEW FROM LE MANS

```render_a2sketch
      #-----------------------------------------------------------#    
      |[q]                                                        |    
      |                                                           | 
      |                                                           | 
      |                                                           | 
      |   Program to where the performance puck is going to be,   | 
      |   not where it has been                                   |        
      |                                                           |
      |                                  - DHH                    |    
      |                                                           | 
      |                                                           | 
      |                                                           | 
      #-----------------------------------------------------------#    

[q]: {"a2s:type": "quote-sw", "a2s:delref": true, "fill": "#27bdce", "fillStyle": "solid"}
```

<div class="tiny">Source: D.H. Hansson. 2016. <a href="https://m.signalvnoise.com/program-to-where-the-performance-puck-is-going-to-be-not-where-it-has-been/">Signal v. Noise</a>.</div>

<aside class="notes" data-markdown>
Disclaimer: this is a very rare point of disagreement with DGG. What is more, his specific point in the blog post (the exceptional performance gains of ARM chips) is indeed remarkable. The question is what should be done with these gains considering that, like the gains predicted by Moore's Law, they cannot go on forever.
</aside>

# THE MISSING THREE PER CENT

```render_a2sketch
#-----------------------------------------------------------#    
|[q]                                                        |    
|                                                           | 
|                                                           | 
|                                                           | 
|       We should forget about small efficiencies,          | 
|       say about 97% of the time:                          |                          
|       premature optimization is the root of all evil      |
|                                                           |    
|                                  - Donald Knuth           | 
|                                                           | 
|                                                           | 
|                                                           | 
#-----------------------------------------------------------#    

[q]: {"a2s:type": "quote-se", "a2s:delref": true, "fill": "#ef5ba1", "fillStyle": "solid"}

```

<div class="tiny">Source: D. Knuth. 1974. &ldquo;Turing Award Lecture.&rdquo; <em>Comm. ACM</em> 17 (1974), p. 671.</div>

<aside class="notes" data-markdown>
In fairness, Knuth goes on to stress 'that critical 3%', but that part is rarely emphasised.
</aside>

# ASYMMETRY

```render_a2sketch
       ^
       |.---------------------------------------.    
 gains ||[c]                                    |    
       ||                                       |    
       ||                                       |
       ||                                       |
       ||                                       |
       ||                                       |
       ||                                       |
       #|                                       #->
       ||                                       |    
       ||                             variable x|    
       ||                                       |    
       ||                                       |    
       ||                                       |    
       ||                                       |    
losses ||                                       | 
       |'---------------------------------------'    
       v

[c]: {"a2s:type": "convex", "a2s:delref": true, "fill": "#fff", "fillStyle": "solid"}
```

<div class="tiny">Adapted from N.N. Taleb. 2012. <em>Antifragile</em>. NY: Random House, p. 273.</div>

<aside class="notes" data-markdown>
Taleb's 'convex' distribution is much less pronounced than this one, but the principle holds.
</aside>

# LENSING {bg=#6a2469 .light-on-dark}

```render_a2sketch
+-+ +-+ +-+ +-+ +-+ +-+ +-+ +-+
+ +-+ +-+ +-+ +-+ +-+ +-+ +-+ +
|                             |
|                             |
|                      NVIDIA |
|                             |
|                             |
+ +-+ +-+ +-+ +-+ +-+ +-+ +-+ +
+-+ +-+ +-+ +-+ +-+ +-+ +-+ +-+

[1,1]: {"stroke": "#fff", "fill": "#fff", "fillStyle": "solid"}
```

```c++
qcl::environment env;
const cl::Platform& platform =
  env.get_platform_by_preference({"NVIDIA", "AMD", "Intel"});
qcl::global_context_ptr global_ctx =
  env.create_global_context(platform, CL_DEVICE_TYPE_GPU);

```

<div class="tiny">Source: A. Alpay. 2018. [github.com/illuhad/teralens](https://github.com/illuhad/teralens). Publication forthcoming.</div>

# ENCODING

<img src="assets/images/rossipedia-status.jpg" alt="CPU and memory utilisation before and after switch to Rustlang"/>

<div class="tiny">Source: [twitter.com/rossipedia/status/1101266107178967040](https://twitter.com/rossipedia/status/1101266107178967040).</div>

# MANDELBROT {bg=#fff44d}

```render_vegalite
{
    "$schema": "https://vega.github.io/schema/vega-lite/v2.0.json",
    "data": {
        "values": [
            {"language": "C++", "seconds": 1.51},
            {"language": "C", "seconds": 1.64},
            {"language": "C# .NET Core", "seconds": 11.64},
            {"language": "Rust", "seconds": 1.74},
            {"language": "Go", "seconds": 5.47},
            {"language": "Java", "seconds": 6.96},
            {"language": "Node.js", "seconds": 18.18},
            {"language": "Erlang", "seconds": 110.80},
            {"language": "PHP", "seconds": 118.28},
            {"language": "Lua", "seconds": 261.54},
            {"language": "Python 3", "seconds": 263.04},
            {"language": "JRuby", "seconds": 300},
            {"language": "Ruby", "seconds": 420}  
        ]
    },
    "width": 600,
    "height": 300,
    "mark": { "type": "bar" },
    "encoding": {
        "x": {
            "field": "seconds",
            "type": "quantitative",
            "scale": {
                "domain": [0.0, 450.0]
            }
        },
        "y": {
            "field": "language",
            "type": "ordinal"
        },
        "color": {
            "field": "seconds",
            "aggregate": "max",
            "type": "quantitative",
            "legend": {
                "title": null
            },
            "scale": {
              "range": [ "#27bdce", "#3364c0", "#fe17bf" ]
            }
        }
    },
    "config": {
        "axis": {
            "labelFont": "sans-serif",
            "labelFontSize": 18,
            "titleFont": "sans-serif",
            "titleFontSize": 18 
        },
        "axisX": {
            "labelAngle": 0
        }
    }
}
```

<div class="tiny">Source: [benchmarksgame-team.pages.debian.net](https://benchmarksgame-team.pages.debian.net/benchmarksgame/performance/mandelbrot.html).</div>

<aside class="notes" data-markdown>
The key point to make here is less the specific spread of results but the variation between benchmarks. Golang, for example, scores poorly when binary trees are involved.
</aside>

# MOBILE 
```render_a2sketch
.----------------------.    
|[b]                   |    
|                      |    
|                      |
|                      |    
|                      |    
|                      |    
|                      |    
|                      |    
|                      |    
|                      |    
|                      | 
'----------------------'    

[b]: {"a2s:type": "battery-10", "a2s:delref": true, "fill": "#fff", "fillStyle": "solid"}
```

<aside class="notes" data-markdown>
Extending battery life is only one possible use of performance improvements. They represent design capital that can be spent on thinner and lighter devices, longer battery life or simply snappier response times.
</aside>

# EMBEDDED
```render_a2sketch
.----------------------.    
|[b]                   |    
|                      |    
|                      |
|                      |    
|                      |    
|                      |    
|                      |    
|                      |    
|                      |    
|                      |    
|                      | 
'----------------------'    

[b]: {"a2s:type": "calendar", "a2s:delref": true, "fill": "#fff", "fillStyle": "solid"}
```

<aside class="notes" data-markdown>
If we consider electronics in the built environment (sensors in walls etc.), this capital can help make devices disappear from view or remain active weeks or months longer before losing power.
</aside>

# PAY FOR WHAT YOU USE
```render_a2sketch
.---------------------------.    
|[c]                        |    
|                           |    
|                           |
|                           |    
|                           |    
|                           |    
|                           |    
|                           |    
|                           | 
'---------------------------'    

[c]: {"a2s:type": "coins", "a2s:delref": true, "fill": "#fff", "fillStyle": "solid"}
```

<aside class="notes" data-markdown>
Ideally code that runs twice as fast will cost half as much to run. That was not at all apparent in on-premises datacentres; still not abundantly clear when using virtual machines and later containers; but it is immediately apparent in the serverless model.
</aside>

# MAXIMISE THE WORK NOT DONE {bg=#6a2469 .light-on-dark}

```render_a2sketch
    #-----------------------------------#    
    |[g]                                |    
    |                                   |    
    |                                   |
    |                                   |    
    |                                   |    
    |                                   |    
    |                                   |    
    |                                   |    
    |                                   |    
    |                                   |    
    |                                   |    
    |                                   |    
    |                                   | 
    #-----------------------------------#    

[g]: {"a2s:type": "globe", "a2s:delref": true, "stroke": "#fff", "fill": "#fff", "fillStyle": "solid"}
```

<aside class="notes" data-markdown>
The single most powerful optimisation is choosing to do less. Faced with virtually limitless compute capacity on a planet offering finite resources, this remains as good a recommendation as any.
</aside>

# <small>THANK YOU</small> {bgcss=tw-colorful .light-on-dark}

<small>Slides built with <a href="https://github.com/arnehilmann/markdeck">Markdeck</a><br/>
<i class="fa fa-github" aria-hidden="true"></i> <a href="https://github.com/gerald1248/bottomless-datacentre-slides">gerald1248/bottomless-datacentre-slides</a><br/>
<i class="fa fa-twitter" aria-hidden="true"></i> 03spirit</small>


<img src="assets/images/ThoughtWorks_logo_white.png" alt="ThoughtWorks logo" width="25%"/>
