

# Adding a Research Post

Follow the steps below to create and publish a new research post.

### 1. Create the post file
- Create a new Markdown file under `_posts/`
- You can start by copying the template file:  
  `2026-01-10-template.md`
- Rename the file in this format:  
  `YYYY-MM-DD-post-title.md`
  

### 2. Add assets
- Create a new image folder at:  
  `img/posts/post-title`
- Store all images related to the post in this folder

### 3. Update front matter
In the post’s front matter, fill out all **required** fields:
- `title`
- `description`
- `date`

Set:
- `published: true` when the post is ready to go live
- *(Optional)* `featured: true` to display the post on the home page

### 4. Write the content
- Write the research post using standard Markdown
- Follow the template’s structure for headings, lists, tables, code blocks, and math
- Use the provided format to embed images
- **Use external embeds only for videos** (e.g. YouTube embed links)

### 5. Publish the post
Once everything looks good, run:

```bash

git add .
git commit -m "YYYY-MM-DD-post-title.md"
git pull --rebase origin source
git push
```

# Adding your profile (current members)

Follow the steps below to create and publish your profile page.

### 1. Create the profile file
- Navigate to the `_team/` folder in the repo.  
- Create a new Markdown file using your **first name** (lowercase is fine).  
  - Example: `haimin.md`  
- You can start by copying the template file: `template-member.md`

### 2. Update front matter
In the post’s front matter, fill out all **required** fields:
- `title`
- `job_title`
- etc

Set:
- `published: true` when the profile is ready to go live

### 3. Profile Image 
- **Preferred:** Upload the image to a reliable URL (e.g., hosted externally).  
- **Alternative:** Place it in the repo folder: `img/members/`  
- Update the front matter `image:` field in your Markdown file:  

### 4. Write the content 

Fill in the following sections using Markdown:
- Research Projects 
- Bio
- Add email and other contact links 
- Hobbies

### 5. Publish the post
Once everything looks good, run:

```bash

git add .
git commit -m "Add profile: Your Name"
git pull --rebase origin source
git push
```

# Adding your profile (former members)

Add a new line in `alumni.md`. Please follow the existing format.

# Adding your publication

Add an entry to `_bibliography/references.bib`. Remember to add the `url` and `video` fields if they are available.

# Acknowledgement

This website is built on top of the [xLAB](https://xlab.upenn.edu/) website. We thank them for sharing their template.