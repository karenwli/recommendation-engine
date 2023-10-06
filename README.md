# recommendation-engine
Recommendation engine that matches user with several team options based on both similarity and distribution variables

This engine selects a few recommended groups for a new user to join upon making an account.

In particular, we try to match availability, location, and average skill level within groups. However, it's still important to have an even distribution of skills within the team. For example, it's not very effective to have 5 experts in python but none in machine learning.

Furthermore, certain variables want minimal variability between group members (time zone, availability), while other variables want maximum variability (skill distribution)

**This approach is more of a data engineering approach, since there are different approaches to optimizing each variable. We first take a subset of maximally close groups, and then within that subset search for maximum variability in skill distribution. It would also make sense to consider a more classical machine learning approach, but the curse of dimensionality (5 days + 5 skill proficiencies + timezone = 11 dimensions) is a challenge to generating meaningful suggestions. Also, there is little opportunity for feedback, as most users will not know whether another group would have been a better fit.
