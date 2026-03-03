**Day 9 – Recommendation System (README)**
**Objective**

Day 9 introduces personalization through recommendation systems using collaborative filtering.

we built a system that:

-> maps user interactions to ratings
-> trains an ALS model
-> generates recommendations
-> understands cold start limitations

This is how ecommerce and streaming platforms personalize experiences.

**What does this Sysytem do:**
Unlike classification:

classification → predict a label

recommendation → rank items

Collaborative filtering learns latent relationships between users and items.

It does not require explicit ratings.

Instead, it uses interaction signals.

**ALS (Alternating Least Squares)**

ALS is collaborative filtering:

factorizes user–item matrix

learns latent factors

ranks items by similarity

