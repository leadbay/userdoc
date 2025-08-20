# 🔭 Lenses

Lenses allow you to define filters (such as company sectors and sizes of interest to you) and reuse them later. Super handy when you prospect several disctinct segments at the same time, or when you are selling more than one product.

<div align="center"><figure><img src="../.gitbook/assets/image (2).png" alt="" width="375"><figcaption></figcaption></figure></div>

Pick a lens from the dropdown menu. Whatever changes you make to your filters will remain attached to that lens. Pick another lens and everything changes - the parameters of that new lens get loaded instantly.&#x20;

<figure><img src="../.gitbook/assets/Capture d’écran 2025-08-20 à 10.53.45.png" alt="" width="375"><figcaption></figcaption></figure>

Go to "Lens settings" to create new lenses, rename or delete existing ones.

### Lens Filters

Anything Leadbay knows about a [Lead](../fundamentals/definitions.md#user-content-lead) is potentially a criteria you can use to filter leads. For example, `Location:Paris` can be a criteria, or `size:50-100`, or `sector:Financial Services.`

#### A Union of Several Criteria

Things get cool when you get to specify more then one criteria, e.g., `sector: Financial Services` , `sector:Agriculture` . Leadbay lets you select multiple criteria of the same type, e.g., `sector,` and understands that you looking for a union of possible matches, i.e. for leads who are in any one of the two sectors, either in `Financial Services` or in `Agriculture`.

#### An Intersection of Unions

Things get even more cool when you combine several types of criteria. Let's say that we want to add `size:50-100` to our already defined union of sectors `Financial Services` and `Agriculture` .

Leadbay will understand that you are looking for [Leads](../fundamentals/definitions.md#user-content-lead) that strictly fit the intersection of size criteria (`50-100`) and with the union of `sector` criteria (`Financial Services` or `Agriculture`). This means that a company in Financial Services having 150 employees will not be selected, while a company in Agriculture with 75 employees will be selected.

It's pretty convenient for modeling commonly used real-life criteria.
