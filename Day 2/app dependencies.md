# So much depends upon .... your python app's dependencies

## your requirements.txt file

when you don't specify version you end up with the most recent version of the packages

pipdeptree is a utility that can give you an understanding of the dependencies your dependencies install

subdependencies are still your dependencies - if one of them breaks, your app breaks

We want reproducibility so, one solution is pinned dependencies......but....

you may want to upgrade some of your dependencies

transitive dependencies - it means if two of your deps have teh same dep - you could end up with issues trying to upgrade one of them

pdm - a dependency manager

pdm demo

