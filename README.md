# Literature books: cleaning and visualization

A small data project built on 1500 records from the [Open Library](https://openlibrary.org/developers/api) search API (subject: literature). The notebook goes through the whole process: collecting the data, inspecting it, cleaning it, and then exploring it with different kinds of plots.

## What the notebook does

1. **Collect**: pulls 1500 records from the API page by page and saves them to `literature_books.csv`.
2. **Inspect**: shape, dtypes, missing values, duplicates, unique values per column.
3. **Clean**: drops columns that are mostly empty or just IDs, fills missing values, fixes impossible years, and handles outliers in `first_publish_year` and `edition_count` with the IQR rule.
4. **Visualize**: histograms, line charts, bar and pie charts, a correlation heatmap, scatter plots, a word cloud of titles, and Venn diagrams for language and availability overlaps. A short explanation is written under each plot.

## Running it

```bash
git clone <repo-url>
cd <repo-folder>
pip install -r requirements.txt
jupyter notebook methodologyProject_Visualization.ipynb
```

Run the cells from top to bottom. The first cell needs an internet connection because it downloads the data (it can take a minute). The CSV is not stored in the repo since the notebook generates it.

## Files

```
.
├── methodologyProject_Visualization.ipynb   # the whole analysis
├── requirements.txt
└── README.md
```

## Notes

- The sample is the first 1500 results the API returns for the subject, so it is not a random sample of all books. Conclusions only apply to this data.
- Books older than about 1712 are removed as outliers on purpose, to keep the plots readable.
- Open Library data changes over time, so numbers can be a bit different if you download it again.
