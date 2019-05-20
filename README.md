# Media Analysis: 2020 Democratic Primary

By itself, a single news article tells a story--it gives us a set of facts or observations as well as a perspective to help connect them. Indirectly, however, it provides us a window into the people who wrote it, those who read and trust it, and how their respective worldviews fit into the broader social context.

The media is more than just a contentious account of events and opinions; it is also a <em>tremendous</em> source of quantitative data. By reading thousands of news articles and blogs from across the spectrum of sources, regions, and opinions, we can better understand our national discourse and more accurately make predictions about its direction.

Natural Language Processing--a crucial sub-branch of data science and machine learning--makes this possible. A computer can read huge quantities of text data and, through specialized algorithms, determine the key topics, moments, and trends driving the conversation.

This project aims to use these techniques to evaluate media coverage surrounding the 2020 Democratic presidential primary, offering both quantitative and qualitative analysis of key issues and candidate performance.

The views expressed here are entirely my own. If you happen to disagree with them, please feel free to use the information provided to offer your own views. I believe strongly in the free exchange of ideas, and support good faith debate.

## Types of Analysis
  
Generally speaking, these are the key analytics I will be running on the media dataset:
  
  <b>Share of Voice</b> -- How many distinct news articles mentioned each candidate over a given period of time? This serves to measure      the overall media interest in a candidate.
  
  <b>Density of Voice</b> -- Across all articles, how many times was a candidate's last name mentioned? This helps us understand how    prominently each candidate is being featured in the conversation, especially when compared to the Share of Voice metric. If a candidate's Density of Voice is roughly the same as their Share of Voice, it means they are being mentioned once or twice per article, but otherwise not receiving attention--putting them in "also running" territory. If, on the other hand, a candidate's name is being mentioned frequently in articles, they are likely a key subject.

  <b>Mention Co-Occurrence</b> -- For a given candidate, which other candidates are frequently mentioned alongside them? This helps us determine which candidates the media believes are in direct competition for a particular nomination "lane," and how the media ranks their general viability.
  
  <b>Wordclouds</b> -- To be honest, I've never been a huge fan of wordclouds, but people like them...so here they are. To generate each candidate's wordcloud, I isolated only the sentences in which the candidate was mentioned, removed "junk" words like prepositions and common verbs, and then plotted based on the frequency each word appears.
  
  <b>Automatic Topic Identification</b> -- This technique utilizes unsupervised machine learning to weight words on their relative importance within the conversation, then group individual articles by similarly occuring key words. By determining topics automatically, we can understand which people, issues, or events are "breaking through" in the media.
  
  <b>Named Entity Recognition</b> -- This is a form of information extraction that attempts to use grammatical and syntactical clues--such as adjective/adverb placement or direct/indirect object relationships--to determine important subjects within text. The goal is to automatically identify key people, organizations, places, and ideas that appear within the conversation. This allows us to determine topic networks, and how particular issues or people grow in influence over time.
  
## Data Source

My source of news data for this analysis is Webhose.io, an aggregation service that scrapes thousands of websites in real-time and returns article text and relevant metadata. While an excellent and affordable source of data, it is important to note that Webhose does not have full access to licensed content--that is, media hosted behind a paywall. This obviously limits the degree of precision available to this analysis, but I believe the results are nevertheless representative of the overall sample. There are other, more premum data sources available, but they come at a substantial cost (tens of thousands of dollars), and are outside the scope of this project.

## Key Tools

Python is my primary tool for data acquisition, cleansing, analysis, and visualization. For this project, I work heavily in the NLTK and SciKitLearn libraries. Where appropriate, I will post Jupyter notebooks of particularly relevant or interesting analysis in this Github repository.

I use Tableau for interactive visualization. Dashboards are hosted on Tableau public.

For network analysis, I use Neo4j and NetworkX as my graph engines, and Gephi as my primary visualization tool.
