# Multi-armed Bandits (MAB)


This repository contains the source code for Assignment 2 of COMP90051 Statistical Machine Learning course, Semester 2 2020 at the University of Melbourne

This notebook contains the implementation of several MAB classes, namely:

1. ε-greedy and UCB MABs
2. Off-policy evaluation (Li et al., 2010, 2011)
3. LinUCB contextual MAB (Li et al., 2010)
4. TreeBootstrap contextual MAB (Elmachtoub et al., 2017)
5. KernelUCB contextual MAB (Valko et al., 2013)

## Project Overview

Multi-armed bandits (MABs) are a simple but powerful framework for sequential decision making under uncertainty. Through the 2000s, Yahoo! Research led the way in applying MABs to problems in online advertising, information retrieval, and media recommendation. One of their many applications was to Yahoo! News, in deciding what news items to recommend to users based on article content, user profile, and the historical engagement of the user with articles.

Given decision making in this setting is sequential (what do we show next?) and feedback is only available for articles shown, Yahoo! researchers observed a perfect formulation for MABs like those (ε-Greedy and UCB) learned about in class.

Going further, however, they realised that incorporating some element of user-article state requires contextual bandits: articles are arms; context per round incorporates information about both user and article (arm); and {0, 1}-valued rewards represent clicks.

Therefore the per round cumulative reward represents click-through-rate, which is exactly what services like Yahoo! News want to maximise to drive user engagement and advertising revenue.

Full details of the project can be found in the project specification project2.pdf 

## Dataset Brief Description

The following details may be helpful to understand the structure of dataset.

• 10,000 lines (i.e., rows) corresponding to distinct site visits by users—events in the language of this part; 

• Each row comprises 102 space-delimited columns of integers: 
– Column 1: The arm played by a uniformly-random policy out of 10 arms (news articles); 
– Column 2: The reward received from the arm played—1 if the user clicked 0 otherwise;
– Columns 3–102: The 100-dim flattened context: 10 features per arm (incorporating the content of the article and its match with the visiting user), first the features for arm 1, then arm 2, etc. up to arm 10.
