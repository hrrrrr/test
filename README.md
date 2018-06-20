# Smart Media Tokens
2
​
3
(c) 2017 Steemit, Inc.  All rights reserved
4
​
5
# SMT Whitepaper
6
​
7
This repository contains the LaTeX source code for the SMT Whitepaper. The
8
instructions to clone the repository and build the PDF using pandoc are
9
described below.
10
​
11
# Fast Build
12
​
13
## OSX
14
​
15
* `brew install docker docker-machine`
16
* `brew tap caskroom/cask`
17
* `brew cask install virtualbox`
18
* `docker-machine create --driver virtualbox default`
19
* `eval $(docker-machine env default)`
20
* `make`
21
​
22
## Docker Already Installed, Linux
23
​
24
(This is already in the `Makefile`.  Just type `make`.)
25
​
26
* `docker build -t steemit/smt-whitepaper .`
27
* `docker run steemit/smt-whitepaper > smt-whitepaper.pdf`
28
​
29
# Manual Build
30
​
31
Currently the manual build instructions are for Ubuntu 16.04 or higher but
32
may successfully build on other distributions. Pull requests to update the
33
whitepaper will be gladly accepted and reviewed.
34
​
35
## Install Packages
36
​
37
```bash
38
sudo apt-get update
39
sudo apt install -y texlive-xetex pandoc python3-pip graphviz imagemagick
40
pip3 install matplotlib
41
```
42
​
43
## Compile Images
44
​
45
There are several image files in the `/img/` directory that are generated using the build file. The first time the build is done, and whenever the figures are updated, the images will need to be compiled.
46
​
47
```bash
48
./build.sh
49
```
50
​
51
## Build PDF
52
​
53
Compile using pandoc
54
```bash
55
cd ~/smt-whitepaper/smt-manual/
56
pandoc manual.md --latex-engine=xelatex -o smt-whitepaper.pdf
57
```
58
​
59
After building, the pdf file will be output to `smt-whitepaper.pdf`.
60
