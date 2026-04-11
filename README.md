# PostHog Cordoba

Community events and projects from PostHog meetups in Cordoba, Argentina.

## Structure

```
event-0/              # First event
  index.html          # Gallery of projects
  project-name/       # Each project has its own subfolder
    index.html
```

## Adding a new project

1. Create a new subfolder under the event directory: `event-0/my-project/`
2. Add an `index.html` inside it with your project
3. Add a link to the event's `index.html`:
   ```html
   <li><a class="project-link" href="./my-project/">My Project</a></li>
   ```

## Adding a new event

1. Create a new directory: `event-1/`
2. Copy `event-0/index.html` as a starting point and update the title
3. Add a link to the root `index.html`

## GitHub Pages

The site is deployed via GitHub Actions. Push to `master` to trigger a deploy.
