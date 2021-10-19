# GitTools

## gitfinder

input      websites&#x20;

output    .git leaked&#x20;



### gitdumper

This tool can be used to download as much as possible from the found .git repository from webservers which do not have directory listing enabled.



### Extractor

A small bash script to extract commits and their content from a broken repository.

This script tries to recover incomplete git repositories:

* Iterate through all commit-objects of a repository
* Try to restore the contents of the commit
* Commits are _not_ sorted by date

This can be used in combination with the `Git Dumper` in case the downloaded repository is incomplete.

