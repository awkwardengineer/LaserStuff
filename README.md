# LaserStuff
Laser cut toys for my kid and an experiment in organizing hardware products.  

![Plane](/Photos/20161004_102646.jpg)
![Plane](/Photos/20161005_202721.jpg)

## How to Use this Repository:
Everything you need to build a laser cut aiplane toy (and packaging!) is located or linked in the Manufacturing folder of this repository, including a link to the "recipe", aka the Bill of Materials, which is in a [google doc](https://docs.google.com/spreadsheets/d/1X3RI_gjsAwJpEgVR00CDBcl03ny8ZZEstYcms3ur_6U/edit#gid=0).  

In general, we've found that the repo is a great place to store released manufacturing files, but if Git isn't a natural place to put the design files, we will leave a URL link to the right place from the repo.

That being said, the mechanical design info is in the Mechanical subfolder of the Design Files, including a link to the online [Onshape files](https://cad.onshape.com/documents/5daeb2494fb381e1f3eea91b/v/51914f51fba51aaff4cbab48/e/80103d4134765a2311185416) where the mechanicals were originally designed.

The packaging label design files were created in Inkscape v0.92 and are in the Packaging subfolder of the Design Files. PDFs for actually printing the labels are, naturally, in the Manufacturing folder.

### Project goals
One of the goals with this project is to try out a different way of using git to organize a hardware repo. There's a lot of thought that went into this and I'll try to summarize the logic that went into it, or at least the underlying philosophies that we're trying to live by.

### Some background on Product Breakdown Structure  
We firmly believe that the repo folder structure should mirror that of the [Product Breakdown Structure](https://en.wikipedia.org/wiki/Product_breakdown_structure). In short, we try to organize a repo to reflect how things are physically built, not necessarily how they logically function. We also try to store engineering design analysis, test reports, etc, at the appropriate system, assembly, or component level of the repo.

**LaserStuff**  
|  
|--Manufacturing Files / Build log  
|&nbsp;&nbsp;&nbsp;|--01 test build  
|&nbsp;&nbsp;&nbsp;|--02 pilot build  
|&nbsp;&nbsp;&nbsp;|--03 **new builds would go here**  
|  
|--Design Files  
|&nbsp;&nbsp;&nbsp;|--Mechanicals   
|&nbsp;&nbsp;&nbsp;|--Packaging   
|  
|--Photos  

### Hardware is more linear
While Github is great for managing the so-called "gitflow" workflow, hardware tends to follow a much more linear path, albeit with one very important exception: every time something is built, it creates a fork off the main linear engineering path that is never folded back in. That is because that build creates a "release" that is now literally and figuratively in the wild. That fork will exist until that physical version of the product is destroyed and gone forever.

As a consequence, we've come up with an important tenet that we will use to manage branches in git.

###Engineering files vs. Manufacturing files

Here is our main tenet: **The engineering folders of the Product Breakdown Structure should reflect the end point of the linear(ish) engineering development path. The manufacturing folder gets a new sub-folder to capture each fork off the main path as product get physcially built.** 

###Hardware lives on
The idea is that hardware, once built, "lives on". The manufacturing folder, rather than hiding forks behind git "branches", just keeps them in numbered "build log" folders.

###Problems we've had with Git in the past
The biggest problem we've had using git in the past is managing multiple integrated parts of a hardware product in one repo. That means tracking mechanicals, electronics, software, and firmware. We tended to have individuals work on mulitple things at once and it became completely cluttered as to which subdiscipline the commit was in regards to. 

This can be addressed by being super careful about working on one thing at a time, being super careful about switching branches, using git submodules and pulling them together into one bigger repo (which is on the advanced side with the added complexity of managing multip repos), or we will try our new plan, which is as follows:

- we want to see a clean branch for mechanicals, firmware, electronics, manufacturing etc...  
- we'll set the branches up from the start  
- and we'll check the repo out multiple times to multiple folders for each top level folder of the Product Breakdown Structure. we're hoping by the time we're done, we'll have a nice pretty [network graph](https://github.com/awkwardengineer/LaserStuff/network) to show.  
