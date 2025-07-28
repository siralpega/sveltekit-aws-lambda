# svlete-aws-lambda
**This is a fork of [https://github.com/anasmohammed361/sveltekit-aws-lambda](https://github.com/anasmohammed361/sveltekit-aws-lambda)**

This is a Svelte Adapter for AWS Lambda. My setup is Cloudfront -> Lambda Function for SSR (build folder), and Cloudfront -> S3 for Static Assets (out/client folder).

---

### svelte.config.js

```
import { adapter as lambdaAdapt } from '@siralpega/sveltekit-lambda-adapter';
import adapter from '@sveltejs/adapter-node';

export default {
	kit: {
		adapter: process.env.BUILD_MODE == "lambda" ? lambdaAdapt() : adapter(),
	}
};
```
---
### build.js

```
import { bundleApp } from "@siralpega/sveltekit-lambda-adapter";
bundleApp()
```
---
# Build app

```bash
npm run build
```
```bash
node build.js
```

