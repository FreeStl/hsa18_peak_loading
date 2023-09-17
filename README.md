# Description
Describe solution that solves peak loadings problem for biggest european football website https://goal.com:

- MAIN PAGE. The first page that user sees when open website. Contains news outlines and current math highlights. Has many static content (pictures).
  - Use CDN to quickly deliver static content.
  - Use NGINX caching to cache pictures.
  - Use short time local caching
  - Use autoscaling.
  - Manually scale up the backend system during popular matches
- LIVE SCORES. This is probably most popular page. Most of the new users click it first. Regular users probably have in in bookmarks.
  - Not much content except match scores, so local cache with extended cache time could be used there for all js code and static content. Calls to BE should be fast.
  - Use autoscaling.
  - Manually scale up the backend system during popular matchesc
- MATCH DETAILS. This page will be constantly updated for popular match, since fans want to get most recent data.
  - Same recommendations as for LIVA SCORES page.
  - Use local autoscaling and CDN. Usually popular matches have most views from countries where teams come from.
- LATEST NEWS. A lot of static content. Content isn't as much dynamic as score page, so it can be cached for longer time
  - Use CDN to quickly deliver static content.
  - Use NGINX caching to cache pictures.
  - Use local caching
  - Use autoscaling.
  - Manually scale up the backend system during popular matches and hot events in the industry
  - Since comments are managed by third-party 
- WORLD CUP / PREMIER LEAGUE.
  - Manually scale up backend during active phase of events. People usually like to check the league status after each match.