# Wikishop – TF-IDF text classification
Study project to practice skills of text preprocessing and solving the problem of text classification

## Problem statement

Wikishop online store launches a new service. Now users can edit and supplement product descriptions, as in wiki communities. That is, clients offer their edits and comment on the changes of others. The store needs a tool that will search for toxic comments and send them for moderation.

## Goal

Train the model to classify comments into positive and negative. At your disposal is a data set with markup on the toxicity of edits.
Target quality metric *F1*: at least 0.75.

## Data description

The data is in the file `toxic_comments.csv'. The *text* column in it contains the comment text, and *toxic* is the target attribute.
