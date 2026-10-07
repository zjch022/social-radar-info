# Social Radar

Social Radar is a personal, non-commercial monitoring and content-discovery tool for public Reddit discussions.

This repository is a public project-information page for API review. The application source code and operational configuration are maintained privately.

## Purpose

Social Radar helps a single user keep up with relevant public discussions without repeatedly browsing multiple communities manually. It periodically checks a limited, user-configured set of public subreddits and public user submissions, ranks relevant discussions, and surfaces a small number of candidates for personal review.

Example topics include SEO, website growth, technology, software development, and AI products.

## Reddit Data API usage

The application is intended to use the Reddit Data API with OAuth and only the data needed for the monitoring workflow, such as:

- post ID and permalink
- title and post body
- author and subreddit
- creation time
- score and comment count

The data is used to identify recent, relevant discussions and basic engagement signals. Selected results are delivered to the user's private notification workflow so the user can decide whether to open and participate in the original Reddit discussion.

## Access pattern

The application:

- reads public Reddit content only;
- runs periodically rather than continuously;
- monitors a limited set of explicitly configured communities and public authors;
- is designed to stay within Reddit's published API rate limits;
- does not attempt to bypass access controls or rate limits;
- does not automatically post, comment, vote, send messages, or perform moderation actions;
- does not access private Reddit content;
- does not sell or redistribute Reddit data;
- does not use Reddit data to train an AI/ML model.

## Why an external application

Social Radar is an external personal workflow rather than a community-embedded Reddit application. It needs scheduled processing, private monitoring state, ranking logic, and integration with an external private notification workflow. The primary interface and processing therefore operate outside Reddit.

## Architecture

```text
Reddit Data API (OAuth)
        |
        v
Private backend
        |
        v
Private application database
        |
        v
Relevance / engagement ranking
        |
        v
Private personal notifications
```

## Status

The project is currently for personal, non-commercial use. API access is being requested for this use case.

## Contact

Project owner: [zjch022](https://github.com/zjch022)
