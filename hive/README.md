# The relationship between ECI, GDP and Gini



The UNDP’s Regional Bureau for Africa and The New School developed a partnership where students from the MSc in Data Visualization work to tackle new ways of seeing inequality and how it works in different scenarios.

In Fall 2017, my class were given the task to create new projects with data from the UNDP report *Income Inequality Trends in sub-Saharan Africa*. The idea behind it was to enhance knowledge and interest on the theme.

I've developed a web-based interactive data visualization looking into the ECI, an index that tracks how a country can grow their infrastructure, along the GDP and GINI. It's a a parallel coordinate graphic, where we see the 3 statistics and their relation for each country in the sub-Saharan Africa. It also gives a more nuanced view for each stat when you click on a line or country name: a bar chart showing the last 20 years of data.

The site's live here:
[https://pessoaflavio.github.io/major-studio-01/assignments/04UserCases/
]()

And code's here:
[https://github.com/pessoaflavio/major-studio-01/tree/master/assignments/04UserCases]()

### FORMAT/STRUCTURE

The UNDP’s Regional Bureau for Africa was interested in different ways of visualizing their data on the report. So what I did was to analyze one possible factor that drives inequality. 

The ECI (Economic Complexity Index) was one of the most fascinating to me: it's a scale that shows how much a  country can grow its manufacturing and industry sector, and it also can be a factor that drives inequality. My idea was to see if we could show the influence of the ECI on things the general public could understand better, like the GDP or the GINI coefficient. 

After setting on this specific question, I started a small sprint, drawing quick sketches to see what could make the most sense.

### DESIGN

I've chosen the parallel coordinates as the main component of the visualization. It fit my intent to show 3 different variables with different scales, and it makes it easier to the reader to find patterns.

To have more background on each index (and also to highlight how sparse some of the data is), the reader could click on a specific line/country and it would reveal historical data on every index, going back 20 years, as bar charts.

The first sketch of the parallel coordinates was the starting point of structure, and developed a grid where header, context and secondary graph were then structured around.

The look and feel were driven more from a practical point, where I developed a color scheme and more clean structure/typography, where it'd also be easier to iterate and do modifications during development time.

### SCOPE
The brief of the partnership was open enough, so every person could suggest a specific theme, and how to develop it. It was during the last past of the Semester, around 2 months, between:

1. Choosing a theme – That was a simple task: after reading the report, I've decided to pick something that was challenging enough to explain to others (the ECI)
2. Reading about it, finding data sources and exploring more context – After picking it, we've cleared with the UNDP communication contact, to see if everything was interesting and connected enought with the project. That led to more research on the ECI, but in the end I was more interested in *showing* data influence, not explaining it verbally. This was a nice constrain for me, to grasp the concept in a more intuitive way. It also meant that I had to find more data sources, and to check their quality and integrity between our group and UNDP as well. This was one of the most crucial points, because it drove the development of the actual final product.
3. Iterations and sketches – They were done around 2 to 3 weeks of coming back and forth with roughs and more full-out specs, and also some feedback with our UNDP contact. Design time was also helpful in creating a more realistic mock-up that was loaded as an SVG initially, to understand limits to legibility and to understand interactive features as well.
4. Coding and production – The design specs were done to make things as quick as possible. The final deliverable was a functional web application, with real data, to be presented to a group of stakeholders (the UNDP office, including the chief economist responsible for the report). Also, limiting the scope of my original question (what does the ECI does to other data?) made things more approachable on the size of the dataset, what needed to be delivered and technologies needed. I've made also a choice of dealing with just a regular full-size version, since it made more sense to have something working good on one resolution.

### DEVELOPMENT AND CODING

The scope and roadmap helped to shape my decisions around what technology I'd use to build my visualization. Since we needed to present our argument in 1 strong and clear manner, and that the visualization would also be shared later, I've narrowed down on creating a webpage (HTML and CSS) that would load an interactive graph, with some extra features, using plain Javascript and D3.

D3 was something that I could use with ease. It also was a dataset small enough so the browser could deal with the SVGs and transitions with no bigger concerns around loading time and browser compatibility. Since everything rendered on the browser was native to the DOM, it made things easier when I needed to change specific typographic choices or styling elements of my graph: I just needed to change my CSS and reload to see a new choice working.

The HTML was made simple enough: I've decided to focus during development time on the Javascript/Dataviz part. It's some simple DIVs, styled in a fixed manner.

I have 2 Javascript files. One is the Main one, called script.js, the other one is BarChart.js. 

1. script.js – This one initiates new BarChart objects, from the BarChart.js, and it also run methods related to these new Objects. It then loads our main Data, draws the main parallel coordinates, styles it and groups everything. It also creates run an Update method for the Bar Chart objects when we interact with the lines. https://github.com/pessoaflavio/major-studio-01/blob/master/assignments/04UserCases/script.js
2. BarChart.js – Deals with all the drawing of the secondary bar chart, and it also creates the functions that will be called in the main script. https://github.com/pessoaflavio/major-studio-01/blob/master/assignments/04UserCases/BarChart.js

The main script was all developed out of the box, and the BarChart update pattern was based on an online example that needed to be updated to D3 v4 and fitted to specifics of the visualization. 

The modularization of my application made things easier to debug and develop, and also made it easier to create the data strucuture behind it (my JSON file).

### WHAT WENT WELL

The feedback for the project was good; the idea behind understanding in pure visual way what the ECI could do was clear, and the secondary data was a nice plus. The researchers and economists in the UNDP felt that it had good potential of even changing the variables to other ones, so they could understand different scenarios. It was also good to develop something in such a quick manner, while doing other projects, and also a first for real experience with D3 as a library.

### WHAT WOULD I CHANGE

I'd have used Flexbox to build the skeleton of the project, so it could makes thing easier when thinking about how much space to use for a specific pattern or graphic, and it would also nice to iterate with it to do a mobile version.

Interactivity was one thing I'd also refine: I didn't have time to develop proper hover-state tools, so we could see actual numerical values for everything. To compesate, I've added some dynamic stats on the top of the bar charts, but they aren't as clear as I thought they would be.

I'd also make some visual and textual changes for my y-axis on both graphics: the direction of my range is very specific for each one of the indexes, and it's somewhat confusing on a glance. I'd make more changes on that.


