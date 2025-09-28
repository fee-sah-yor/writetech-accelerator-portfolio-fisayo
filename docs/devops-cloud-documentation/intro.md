# Understanding CI/CD Workflows as a Beginner

## What is CI/CD?
Dearest gentle reader, if you’re reading this, then I finally wrote the simplest article you’ll ever come across concerning CI/CD. I say this because my goal is to give you a basic understanding of the CI/CD concept in a single-page document—so stay with me, please.
Continuous Integration (CI) and Continuous Deployment (CD) are two closely linked concepts. They work as a team and are used in many tech teams globally.

**Continuous Integration (CI):** the process of automatically checking and testing new changes before they are merged into the main project. Think of it as a way to catch issues early, so problems don’t pile up.
**Continuous Deployment (CD):** the process of automatically delivering those verified changes to production (to users). Once your code passes the CI checks, it gets deployed without manual effort.


## My Cooking Analogy 🍲👩🏽‍🍳
Imagine this: a menu is to be prepared, and each chef is asked to pick their preferred meal and go ahead to cook with their own style. They chop, fry, and spice however they like. Now, when it’s time to bring everything together, it’s chaos:
- Some chefs cooked the same dish twice.
- Vegetables are cut in all sorts of sizes.
- The taste isn’t consistent—some went heavy on spices, others used none.
A fine mess.

Now imagine if the menu was broken into stages:
- Each chef sends their chopped veggies to the main chef (CI), who checks them for uniformity.
- The broths are tasted and corrected to follow the laid-out spice rules.
- Only after this review does the meal get accepted into the menu.

This is what CI does—it breaks down a big task into smaller, manageable steps, so reviews are quicker and issues are spotted early.
CD takes it further: once the menu is approved, it’s automatically plated and served to guests at any time. No scrambling last minute. That’s Continuous Deployment. Together, CI and CD are like two peas in a pod—they keep tech teams working smoothly and efficiently.

## Diagram of CI/CD
<div style={{ display: "flex", justifyContent: "center" }}>
  <img src="/img/flowchart.png" alt="tutorial with default dots and buttons" width="300" />
</div>

## Example of a CI/CD File (GitHub Actions)
This CI/CD file was created using GitHub Actions. GitHub runs actions when conditions for the workflow are met. The file lives inside the .github/workflows folder.
Think of it like a document that tells each chef what to do, so the main chef doesn’t have to shout orders. It uses a .yml extension and the number one rule to follow when writing YAML is indentation.

**Example:**
```bash
name: CI/CD Pipeline
on:
 pull_request:
   branches:
     - main


jobs:
 # CI Step: Run tests on every PR
 test:
   runs-on: ubuntu-latest
   steps:
     - name: Checkout code
       uses: actions/checkout@v3


     - name: Setup Node.js
       uses: actions/setup-node@v3
       with:
         node-version: 18


     - name: Install dependencies
       run: npm install


     - name: Run tests
       run: npm test


 # CD Step: Deploy after merge into main
 deploy:
   needs: test
   if: github.ref == 'refs/heads/main' && github.event_name == 'push'
   runs-on: ubuntu-latest
   steps:
     - name: Checkout code
       uses: actions/checkout@v3


     - name: Setup Node.js
       uses: actions/setup-node@v3
       with:
         node-version: 18


     - name: Install dependencies
       run: npm install


     - name: Build project
       run: npm run build


     - name: Deploy to Vercel
       uses: amondnet/vercel-action@v25
       with:
         vercel-token: ${{ secrets.VERCEL_TOKEN }}
         vercel-org-id: ${{ secrets.ORG_ID }}
         vercel-project-id: ${{ secrets.PROJECT_ID }}
         working-directory: ./

```

CI Step: Runs tests automatically when you open a pull request (like checking veggies before they reach the menu).

CD Step: Deploys the app once everything is approved and merged (like plating and serving the food).


## Conclusion

The use of CI/CD pipelines in any team results in one thing: clear, repeatable, automated systems. Workflows run smoothly without constant human interference—unless, of course, there’s a bug to fix.
With CI/CD, you can build pipelines that catch problems early, speed up development, and give teams more confidence when shipping updates.
There are many more advanced ways to use CI/CD, but I hope this article gave you the basic understanding you need to get started.
Thank you.

