# 💝 Understanding Wishlists

## How Wishlists Work

[#user-content-wishlist](../fundamentals/definitions.md#user-content-wishlist "mention")s are the core of Leadbay experience. They allow you to define the qualities that make a [#user-content-lead](../fundamentals/definitions.md#user-content-lead "mention") interesting for you, i.e. that allow to consider a Lead _qualified_.&#x20;

Wishlists are defined dynamically, using criteria that are then constantly being matched against the ever growing (and changing) Leadbay database. As their situation changes (e.g. the size of the company changes), Leads may automatically get included in the selection or drop out of it.

### The Basics

Anything Leadbay knows about a [#user-content-lead](../fundamentals/definitions.md#user-content-lead "mention") is potentially a criteria you can use to specify leads of interest and shape your [#user-content-wishlist](../fundamentals/definitions.md#user-content-wishlist "mention"). For example, `Location:Paris` can be a criteria, or `size:50-100`, or `sector:Financial Services.`

``p.s. We are working on adding new cool criteria such as `lookalikesOf:Leadbay` or `competitorsOf:Leadbay`.``

### A Union of Several Criteria

Things get cool when you get to specify more then one criteria, e.g., `sector: Financial Services` , `sector:Agriculture` . Leadbay lets you select multiple criteria of the same type, e.g., `sector,` and understands that you looking for a union of possible matches, i.e. for leads who are in any one of the two sectors, either in `Financial Services` or in `Agriculture`.

### An Intersection of Unions

Things get even more cool when you combine several types of criteria. Let's say that we want to add `size:50-100` to our already defined union of sectors `Financial Services` and `Agriculture` .

Leadbay will understand that you are looking for [#user-content-lead](../fundamentals/definitions.md#user-content-lead "mention")s that strictly fit the intersection of size criteria (`50-100`) and with the union of `sector` criteria (`Financial Services` or `Agriculture`). This means that a company in Financial Services having 150 employees will not be selected, while a company in Agriculture with 75 employees will be selected.

It's pretty convenient for modeling commonly used real-life criteria.

### A Union of Intersection of Unions

Things get really cool when you define Union of Intersection of Unions. We know, it's geek stuff! But soon you'll want to select all the Leads in `Paris` or `Lyon` sized `50-100` and all the leads in `London` sized `200-500`.&#x20;

This is currently not supported. We are working on an interface that makes it easy. Stay tuned.
