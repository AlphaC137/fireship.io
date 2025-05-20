# Fireship.io

The [Fireship PRO](https://fireship.io) course platform frontend built with:

- Svelte
- Tailwind CSS
- Hugo (Static Site Generator)
- Firebase
- Flamethrower (Router)

## Contributing

All static content is managed with Hugo in the `content` directory. You can easily fix typos by modifying the markdown directly in GitHub.

### Prerequisites

1. Install [Hugo Extended](https://gohugo.io/getting-started/installing/) version `0.101.0` or greater
2. Node.js 16+ and npm
3. Firebase CLI (optional, for deployment)

### How to Run it

```bash
git clone https://github.com/fireship-io/fireship.io
cd fireship.io
npm install
npm start
```

Visit `http://localhost:6969/` in your browser.

### Development Scripts

- `npm start` - Start the development server
- `npm run build` - Build the project for production
- `npm run check` - Run Svelte type checking
- `npm run lint` - Lint the codebase
- `npm run lint:fix` - Automatically fix linting issues
- `npm run deploy` - Deploy to Firebase hosting


## Developing Components 

Create a Svelte file in the `app/components` directory. It must have a custom element tag. 

```svelte
<svelte:options tag="hi-mom" />

<script>
    export let greeting: string;
</script>

<h1>Hi Mom! {greeting}</h1> 
```

Export the component from `app/main.ts`:

```ts
export * from './components/hi-mom.svelte';
```

Now use it in anywhere in your HTML or Markdown. 

```html
<hi-mom greeting="i made a web component"></hi-mom>
```

**Note:** A weird caveat with Svelte web components is that all styles must be encapsulated. You can use Tailwind, BUT only with `@apply` in the component. Global styles will not work.

## Commands

- `npm start`: Main dev server. Runs everything you need. 
- `npm run dev`: Runs components in isolation. Serves `app/index.html` as a playground for components. 
- `npm run hugo`: Only runs static site. 
- `npm run build`: Build for production
