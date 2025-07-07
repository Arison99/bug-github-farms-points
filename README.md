# Auto Farms Points
## BUG in Github
#### Author: Bocaletto Luca

Hi there! I’m Luca ([@bocaletto-luca](https://github.com/bocaletto-luca)), and I’ve put together this repo to demonstrate a surprising “feature” (or vulnerability?) in GitHub’s contribution model. With a single workflow file, you can automatically farm commits, issues, PRs, wiki edits, releases and comments every hour—artificially inflating your contribution graph.

Feel free to explore, reproduce, and share feedback. If you agree this could be abused at scale, please consider upvoting my [feedback issue on GitHub](https://github.com/github/feedback) or submitting your own.

[![Read Online](https://img.shields.io/badge/Read%20Online-Here-blue?style=flat-square&logo=github)](https://github.com/bocaletto-luca/bug-github-farms-points/index.html)

---

## 📄 Proof of Concept

You can find the full workflow YAML in the root as  
**bug-github-farms-points.txt**  

To try it yourself:

1. **Clone** this repo.  
2. **Rename** `bug-github-farms-points.txt` to  
   `.github/workflows/super-farm-points.yml`  
3. **Commit & push** to your own repository.  
4. Wait for the next hour tick (or run the workflow manually).  
5. Watch your contribution graph skyrocket with automated activity!

---

## 🔍 What’s happening under the hood

Inside the workflow you’ll see jobs that, every hour:

- Generate multiple commits by overwriting a tiny file.
- Open & close issues  
- Create, merge & clean up pull requests  
- Update the repository wiki  
- Tag & publish GitHub Releases  
- Comment on the latest issue  

All of this runs under **one workflow** and uses only GitHub’s official Actions tokens and APIs.

---

## ⚠️ Impact

- **Inflated metrics**: The contribution graph can be “gamed” without manual work.  
- **Resource consumption**: Free-tier minutes and API rate limits could be wasted.  
- **Misleading signals**: Recruiters, collaborators or open-source maintainers may be misled by high activity.  
- **Potential policy violation**: GitHub’s Terms of Service discourage abuse of automated workflows and spam.

---

## 🛠 Suggested Mitigations

1. **Distinguish human vs. scheduled**  
   - Exclude commits made by scheduled workflows from contribution counts.  
2. **Rate-limit scheduled contributions**  
   - Cap the number of workflow‐generated commits/issues per day.  
3. **Flag detected patterns**  
   - Alert users or admins when a single workflow generates high-volume activity.  
4. **Opt-in for counting scheduled events**  
   - Let users choose whether scheduled runs should appear in their public graph.

---

## 🤝 Responsible Disclosure

I’ve also contacted GitHub Security (security@github.com) with this Proof of Concept. My goal is to help make GitHub metrics more trustworthy and to highlight how automation can be misused. If you’re a security researcher or GitHub staffer, you’re welcome to review and follow up here.

---

## 🚀 Next Steps

- Fork this repo and experiment safely on a throwaway repository.  
- Upvote or comment on my [GitHub feedback issue](https://github.com/github/feedback).  
- Share ideas for community-driven solutions in `docs/suggestions.md` (coming soon!).  
- Spread the word so metrics stay meaningful for everyone.

---

Thanks for checking this out! If you have questions or improvements, open an issue here or reach out on Twitter @bocaletto_luca. Let’s work together to keep GitHub honest—and fun.

Happy farming (but only for demonstration purposes)!  
Luca (@bocaletto-luca)  
