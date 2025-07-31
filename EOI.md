# Expression of Interest submission

## Proposal summary/scope of work
Matplotlib is a library for creating publication-quality data visualisations in Python. It enables research in all disciplines and provides visualisation capabilities for many domain-specific pieces of research software. Matplotlib is 22 years old with a mature code base and governance model, downloaded more than 3 million times on a typical weekday, and primarily developed by a community of volunteers.

Our proposal outlines an approach to improve Matplotlib's long-term sustainability with three categories of work: 1) ongoing maintenance, 2) increasing adoption, and 3) reducing the long-term maintenance burden. These tasks fall outside the scope of what volunteer effort alone can reasonably accomplish, and will ensure Matplotlib continues to provide a free and vital tool for all researchers long into the future.

1. Ongoing maintenance: We will contribute to the general maintenance and community engagement, including fixing bugs, reviewing pull requests, answering user questions, and welcoming new contributors. This will allow us to be responsive to barriers preventing researchers using Matplotlib and accommodate new needs of the research community. We will be able to take on more complex work than can be taken on by part-time volunteer effort alone, while executing critical day-to-day maintenance tasks required to keep the project healthy.
2. Increasing adoption: We will improve support for plotting data with attached physical units (e.g. length, time, temperature...) by documenting the existing (patchy and partial) support across the library. We will develop a design to consistently support data with units, and execute this plan. We will also conduct a full review of the narrative documentation (including existing user guide and tutorials), and make improvements across the board.
3. Reducing maintenance burden: We will carry out two well-scoped projects to reduce the long-term maintenance burden.

A large part of the Matplotlib test suite compares generated images against a 'baseline' expected set of images to catch bugs. These baseline images are stored directly in the Matplotlib source code, so developers are reluctant to add more figure tests to avoid increasing the size of the repository (currently 500 MB). Solutions have been suggested but none implemented yet - in consultation with other developers we will solve this issue, enabling more image tests to be added, catching bugs earlier and speeding up the adoption of new features requested by researchers.

The large test suite and documentation build both take a long time to run. We will profile and improve performance of both the tests and documentation build. For the documentation build in particular, we expect to contribute performance improvements to Sphinx, a documentation system used widely across the scientific Python ecosystem, bringing benefits to developers of other Python packages used in research.

As part of our work the project lead will mentor at least one member of their software development group, aiming for the mentee to become a new active Matplotlib developer themselves. We will also set up a dashboard of metrics to understand how our work has impacted Matplotlib.

## Categories of work
- [x] Technical
- [x] Community
- [x] Documentation
- [x] Training
- [ ] Governance

## Project Team
David Stansby, the Project Lead, is a software developer with nine years experience contributing to and leading open source software communities within the scientific Python ecosystem. He has been an active Matplotlib developer for the last eight years, and has experience leading successful grants to develop related software awarded by the Chan Zuckerberg Institute and the European Union.

Lucy Caselton, the documentation specialist, is a Professional Research Investment and Strategy Manager (PRISM) with 20 years experience of document writing (including user guides, work instructions and protocols) for medical imaging NHS staff and researchers, and building documentation repositories (GitHub and Q-Pulse). Lucy has previously run online user training sessions and created video tutorials for imaging systems and platforms, such as XNAT[1] and the OHIF viewer [2].

Both are based in the Centre for Advanced Research Computing at UCL, bringing two significant advantages. Firstly, we are in an ideal location for directly interacting with researchers across all disciplines whose research is enabled by Matplotlib. Secondly, we are surrounded by research software engineers of various experience and expertise in Python open source development, who will be able to provide feedback and evaluate our work in improving the Matplotlib developer experience.

- [1] https://www.xnat.org
- [2] https://viewer.ohif.org

## Benefit to UK research
Plotting and visualising results is a critical part of the research pipeline. Matplotlib has enabled much recent transformative UK-led research, including the Nobel Prize winning prediction of protein structure using Alphafold [1], developing new tests for Parkinson’s disease [2], and datasets used as historic climate benchmarks [3]. Matplotlib is also used across a wide breadth of research areas - examples of recent research enabled by Matplotlib and funded by all seven research councils are given below.

Although it is hard to measure quantitatively how widely used Matplotlib is in the UK, on a global scale estimates of Matplotlib usage on arXiv, a scientific preprint server, indicate it is used by over 20% of all science, a proportion that is only growing with time [4].

- [1] https://doi.org/10.1038/s41586-021-03819-2
- [2] https://doi.org/10.1093/brain/awab306 
- [3] https://doi.org/10.1029/2019JD032361
- [4] https://docs.coiled.io/examples/arxiv-matplotlib.html 

Recent research enabled by Matplotlib, funded by all seven UK research councils:
- AHRC: https://doi.org/10.1016/j.ipm.2024.103910 
- BBSRC: https://doi.org/10.1016/j.foodchem.2024.141537 
- EPSRC: https://doi.org/10.1016/j.neucom.2024.128659 
- ESRC: https://doi.org/10.1136/bmjopen-2024-087946 
- MRC: https://doi.org/10.26508/lsa.202402787 
- NERC: https://doi.org/10.1051/swsc/2024024 
- STFC: http://dx.doi.org/10.3847/psj/ad9565 

## Landscape analysis
Matplotlib is the primary open source software package used for creating publication quality figures within the Python ecosystem.

Other proprietary software used by the research community for 2D data visualisation includes Microsoft Excel, MATLAB, Prism, and OriginPro. These are all also mature packages, but because they are closed-source products we do not know how popular they are.

Similar open-source software used for research outside the Python ecosystem includes ggplot2 (in the R ecosystem), Plots.jl (in the Julia ecosystem, which can optionally use Matplotlib as a backend), and gnuplot. Although we do not have data for researchers specifically, a survey of general software developers [1] indicates Python is significantly more widely used (by 50% of programmers) compared to R (4%), MATLAB (4%), and Julia (1%). A survey of research software engineers [2] indicates similar trends: Python used by 71%, R by 27%, Matlab by 13%, Julia by 7%.

Within the Python ecosystem, many other popular packages offer plotting capabilities, but tend to be targeted at use cases other than creating static plots for publication. Examples include Plotly and bokeh for interactive plots and dashboards, or PyQtGraph for real time data visualisation. Vega-Altair offers similar end results to Matplotlib, using a different style of programming. It is less popular than Matplotlib, with ~1 million downloads/day compared to Matplotlibs ~3 million downloads/day.


[1] https://survey.stackoverflow.co/2024/technology#most-popular-technologies
[2] https://softwaresaved.github.io/international-survey-2022/section/tools-and-programming-languages/#world 

## Measure of impact
Briefly describe how you would measure the impact of the proposed work. You may have existing measures that you use, or you may propose new measures. For the Expression of Interest we are looking to understand how you would approach this, and what you think is important to measure. In the full application, you will be asked to define specific measures (250 words)

The main goal of our project is to make it easier for researchers to use Matplotlib as part of their research pipeline, by supporting the development and maintenance of the software. The current bottleneck to development and maintenance is a shortage of maintainer time to review volunteer work. As such, we have chosen several metrics defined by the Community Health Analytics in Open Source Software (CHAOSS [1]) that we think will track activities to increase the number of maintainers. This includes making it easier for first contributors to transition into regular maintainers, by improving the overall development experience.

The metrics fall under three key areas:

### Reducing development overheads
Time taken to execute tests (lower = better)
Time taken to build documentation (lower = better)
Complexity of developer setup guide (shorter/less steps = better)

### Increasing development capacity
Successfully mentoring a new core developer
Merged pull requests by non-core contributors (more = better)
Number of second contributions merged (more = better)

### Responding to the needs of the research community
Number of bugs fixed (higher = better)

As part of our project we will set up a dashboard to track these metrics over time using tools already developed by the CHAOSS community. We will ensure this dashboard is robust and maintainable to last beyond the grant period.

[1] https://chaoss.community 
