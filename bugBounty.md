-Bug bounties should not be a substitute for quality assurance, testing, or a security program.  Companies should not be relying on outsiders "to fix basic errors that in-house teams should have spotted themselves"
REF: https://www.zdnet.com/article/meet-the-hackers-who-earn-millions-for-saving-the-web-how-bug-bounties-are-changing-cybersecurity/
---
-Web scraping
-Before you scrape a website you should check if it allows crawling or no which is usually in the site's robot.txt.  EG. [website URL]/robots.txt
-A website that blocks all user agents set the following rules:
	user-agent: *
	Disallow: /
OR to block certain directories or pages
	user-agent: *
	Disallow: /URL to page 1
	Disallow: /URL to page 2

REF: https://www.makeuseof.com/is-web-scraping-illegal/?utm_source=MUO-NL-RP&utm_medium=newsletter
