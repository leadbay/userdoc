# 🏅 Understanding Scoring

Our AI selects the key [#user-content-attribute](../fundamentals/definitions.md#user-content-attribute "mention")s and their values that play a role in raking your leads.

<figure><img src="../.gitbook/assets/scoring.jpg" alt=""><figcaption><p>Scoring configuration</p></figcaption></figure>

You can ajdust the importance they have manually and directly see how it impacts the ranking of the list.

Moving the slider to the left will add negative points to the the attribute value, and moving the slider to the right will add positive points.&#x20;

In the end, whatever the number of attributes the final score is projected to the 0-100 scale for convenience.

### Understanding the score

The score reflects two types of criteria:

* The scoring criteria you define, and the importance you set for each of them
* What our AI thinks are leads likely to have affinity for your products and services

Leadbay takes all those factors into account, sources leads that fit to them, and then ranks them. Highest ranking leads, the ones that fit best the criteria you defined, will have a score closer to 100.

Past closed (`won` or `lost`) leads are not scored. Only the leads suggested by Leadbay, or those being actively pursued (`wanted`) are subject to scoring.
