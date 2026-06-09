{
  "title": "KDP Coloring Book Niche Analyzer",
  "type": "object",
  "schemaVersion": 1,
  "properties": {
    "searchTerm": {
      "title": "Search Term",
      "type": "string",
      "description": "Enter a coloring book niche keyword (e.g. 'mandala coloring book', 'dinosaur coloring book for kids')",
      "editor": "textfield",
      "default": "coloring book"
    },
    "targetAudience": {
      "title": "Target Audience",
      "type": "string",
      "description": "Who is the coloring book for?",
      "editor": "select",
      "enum": ["kids-2-4", "kids-5-8", "kids-9-12", "teens", "adults", "seniors", "all"],
      "enumTitles": ["Toddlers (2–4)", "Kids (5–8)", "Older Kids (9–12)", "Teens", "Adults", "Seniors", "All Ages"],
      "default": "adults"
    },
    "nicheTheme": {
      "title": "Niche Theme",
      "type": "string",
      "description": "Primary visual theme to analyze",
      "editor": "select",
      "enum": ["mandala", "animals", "fantasy", "floral", "stress-relief", "holiday", "educational", "pop-culture", "geometric", "other"],
      "enumTitles": ["Mandala / Zentangle", "Animals & Nature", "Fantasy & Mystical", "Floral & Botanical", "Stress Relief / Mindfulness", "Holiday & Seasonal", "Educational", "Pop Culture & Fandom", "Geometric & Abstract", "Other"],
      "default": "mandala"
    },
    "maxResults": {
      "title": "Max Results",
      "type": "integer",
      "description": "Number of Amazon listings to scrape and analyze",
      "editor": "number",
      "minimum": 10,
      "maximum": 100,
      "default": 30,
      "unit": "listings"
    },
    "minBSR": {
      "title": "Min BSR Threshold",
      "type": "integer",
      "description": "Only include books with BSR above this value (lower = more competitive)",
      "editor": "number",
      "minimum": 1,
      "maximum": 1000000,
      "default": 1
    },
    "maxBSR": {
      "title": "Max BSR Threshold",
      "type": "integer",
      "description": "Only include books with BSR below this value. 150,000 is a good profitability cutoff.",
      "editor": "number",
      "minimum": 1,
      "maximum": 2000000,
      "default": 150000
    },
    "minReviewCount": {
      "title": "Min Review Count",
      "type": "integer",
      "description": "Minimum number of reviews to qualify as validated demand (0 = include all)",
      "editor": "number",
      "minimum": 0,
      "maximum": 10000,
      "default": 10
    },
    "minRating": {
      "title": "Min Average Rating",
      "type": "number",
      "description": "Minimum star rating to include (e.g. 3.5 filters out poor-quality niches)",
      "editor": "number",
      "minimum": 1,
      "maximum": 5,
      "default": 3.5
    },
    "priceRangeMin": {
      "title": "Min Price (USD)",
      "type": "number",
      "description": "Minimum listing price to include",
      "editor": "number",
      "minimum": 0.99,
      "maximum": 99,
      "default": 5.99
    },
    "priceRangeMax": {
      "title": "Max Price (USD)",
      "type": "number",
      "description": "Maximum listing price to include",
      "editor": "number",
      "minimum": 0.99,
      "maximum": 99,
      "default": 24.99
    },
    "pageCount": {
      "title": "Page Count Filter",
      "type": "string",
      "description": "Filter by page count range (affects production cost and perceived value)",
      "editor": "select",
      "enum": ["any", "under-50", "50-100", "100-200", "200-plus"],
      "enumTitles": ["Any", "Under 50 pages", "50–100 pages", "100–200 pages", "200+ pages"],
      "default": "100-200"
    },
    "includeLowContent": {
      "title": "Include Low-Content Books",
      "type": "boolean",
      "description": "Include activity books, trace-and-color, and dot-to-dot hybrids alongside pure coloring books",
      "editor": "checkbox",
      "default": false
    },
    "extractKeywords": {
      "title": "Extract Title Keywords",
      "type": "boolean",
      "description": "Scrape and rank recurring keywords from top-performing book titles",
      "editor": "checkbox",
      "default": true
    },
    "competitionScore": {
      "title": "Calculate Competition Score",
      "type": "boolean",
      "description": "Output a 0–100 niche competition score based on BSR, review count, and price spread",
      "editor": "checkbox",
      "default": true
    },
    "outputFormat": {
      "title": "Output Format",
      "type": "string",
      "description": "How results should be structured in the dataset",
      "editor": "select",
      "enum": ["full", "summary", "keywords-only"],
      "enumTitles": ["Full listing data", "Summary stats only", "Keywords only"],
      "default": "full"
    },
    "amazonMarketplace": {
      "title": "Amazon Marketplace",
      "type": "string",
      "description": "Which Amazon store to scrape",
      "editor": "select",
      "enum": ["amazon.com", "amazon.co.uk", "amazon.ca", "amazon.de", "amazon.fr"],
      "enumTitles": ["US (amazon.com)", "UK (amazon.co.uk)", "Canada (amazon.ca)", "Germany (amazon.de)", "France (amazon.fr)"],
      "default": "amazon.com"
    }
  },
  "required": ["searchTerm", "targetAudience", "nicheTheme", "maxResults"]
}
