---
layout: post
title: Day Eleven - Aha moment
---

Last Friday I chatted with Michael, who was kind enough to tell me all about his experience in data engineering. He practically provided me with a custom curriculum for this area. 

One of the technologies he recommended I look into was polars, a new dataframe library that promises to replace pandas. As I was browsing its website, the phrase "Built in Rust" caught my eye. It was one of those moments where you feel things starting to fall into place. Finally, I saw my disparate interests converging. 

Side note: I haven't even tried polars out, but I was excited to see this in the docs: 

```
df_vertical_concat = pl.concat(
    [
        df_v1,
        df_v2,
    ],
    how="vertical",
)
```

I can't express how much better this is than `axis=0`. It seems like a small change, but naming matters. 
