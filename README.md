# Facebook Political Ad Collector

This repository is no longer maintained and exists for archival purposes only.

For a more recent project on this topic, see
[Ad Observer](https://facebook.com).

<details><summary>See archival README information.</summary>

This is the source code behind our project to collect political ads on Facebook. You can browse the American ads we've collected at, and the Australian ads over on the.

We're asking our readers to use this extension when they are browsing Facebook. While they are on Facebook a background script runs to collect ads they see. The extension shows those ads to users and asks them to decide whether or not a particular ad is political. Serverside, we use those ratings to train a naive bayes classifier that then automatically rates the other ads we've collected. The extension also asks the server for the most recent ads that the classifier thinks are political so that users can see political ads they haven't seen. We're careful to protect our user's privacy by not sending identifying information to our backend server.

We're open sourcing this project because we'd love your help. Collecting these ads is challenging, and the more eyes on the problem the better.

## Run it on your own

You can find instructions on how to set up your own full-fledged version of the Facebook Political Ad Collector in [INSTALLATION.md](INSTALLATION.md)

There is an explanation of all the moving parts in [ARCHITECTURE.md](ARCHITECTURE.md)

## Stories


## Where We Need Your Help

In general, the project needs more tests. We've written a couple of tests for parsing the Facebook timeline in the extension directory, and a few for the tricky bits in the server, but any help here would be great!

Also, the rust backend needs a bit of love and care, and there is a bit of a mess in `backend/server/src/server.rs` that could use cleaning up.


### Types of ads the collector doesn't collect

 - mobile ads
 - pre-roll, midstream video ads
 - video from ads in the stream
 - Instagram-only ads (Note that many ads are set to run on Facebook and Instagram with the same creative)

### TODOs to Consider:

 - considering triggering the ad parsing routine only on scroll, to mitigate the clicking-off problems.
 - consider retaining utm params (i.e. a whitelisted set of parameters in links that are added by advertisers, not by FB and ipso facto are not personally identifiable, e.g. `utm_content`, etc., since those sometimes include useful metadata about the ad.)
 - consider turning off the panelist_ads table, etc. 
 - consider seeding the partisanship model in new languages with political tweets. 

 </details>
