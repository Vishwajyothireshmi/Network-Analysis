# Reddit User Interaction Network Analysis

This project explores community structure and user influence on the "r/AskReddit" subreddit using network science and data collected via the Reddit API. The goal is to identify key user clusters, visualize interactions, and compute influence metrics.

## Objective

Build and analyze a user interaction graph based on Reddit comment replies. The graph helps reveal:
- Community structures within the subreddit
- Influential users based on network centrality
- Users who act as bridges across communities

## Data Collection

Data is collected from Reddit using the PRAW API.

- Subreddit: r/AskReddit  
- Posts scraped: 100  
- Users tracked: ~300  
- Edges: A replies to B → edge from A to B

Example:

```python
reddit = praw.Reddit(
    client_id="YOUR_CLIENT_ID",
    client_secret="YOUR_SECRET",
    user_agent="AskRedditScraperBot/1.0"
)
```

## Tools and Libraries

- Python  
- praw (Reddit API)  
- networkx (Graph construction and analysis)  
- community (Louvain method for community detection)  
- pandas  
- matplotlib and seaborn for visualization  
- nest_asyncio for async support inside notebooks

## Network Construction

- Nodes: Unique Reddit users  
- Edges: Directed connections from reply relationships  
- Graph type: Directed graph (DiGraph)

Each edge indicates a user replying to another user’s comment.

## Analysis Steps

Community Detection:
- Method: Louvain algorithm
- Purpose: Cluster users who interact more frequently with each other

Centrality Metrics:
- PageRank – influence from incoming links  
- Betweenness Centrality – how often a user lies on shortest paths  
- Closeness Centrality – average distance to all other nodes  
- Clustering Coefficient – local tightness of user group

Visualizations:
- Network graph with community clusters  
- Centrality heatmap  
- Distribution plots for user influence scores

## Key Insights

- The network shows a long-tail distribution: a few users dominate in terms of influence.
- PageRank and Betweenness were effective in identifying influential users.
- Certain users bridged multiple communities, making them central to cross-topic discussion.

## Future Improvements

- Add edge weights based on upvotes or comment length  
- Apply sentiment analysis to detect tone and toxicity  
- Compare multiple subreddits for interaction style differences  
- Analyze dynamic changes over time (temporal analysis)

## License

This project is intended for academic and educational use only.

## Author

Vishwajyothi Reshmi  
Master’s Student – Data Science
