<<<<<<< HEAD
# React Static Website Deployment on AWS with Terraform

This project demonstrates how to deploy a React static website to **Amazon S3**, with **CloudFront** as a CDN, all managed using **Terraform**.

## í¼ Live URLs

- **CloudFront CDN URL:** [https://d12215vuojrebb.cloudfront.net](https://d12215vuojrebb.cloudfront.net)
- **S3 Static Website URL:** [http://my-react-bucket-0621.s3-website-us-east-1.amazonaws.com](http://my-react-bucket-0621.s3-website-us-east-1.amazonaws.com)

---

## í³ Project Structure

```bash
.
â”œâ”€â”€ main.tf                # Terraform configuration for S3, CloudFront, and IAM
â”œâ”€â”€ variables.tf           # Input variable definitions
â”œâ”€â”€ outputs.tf             # Output values like URLs
â”œâ”€â”€ build/                 # Production-ready React app files (after `npm run build`)
â””â”€â”€ README.md              # Project documentation
í» ï¸ Prerequisites
AWS CLI configured (aws configure --profile terraformuser)

Terraform installed

Node.js & npm installed

A working React project (npx create-react-app my-app)

íº€ Deployment Steps
1. Build the React App
bash
Copy
Edit
npm install
npm run build
2. Initialize Terraform
bash
Copy
Edit
terraform init
3. Apply Infrastructure
bash
Copy
Edit
terraform apply -auto-approve
You will be prompted to enter the bucket name, e.g., my-react-bucket-0621.

4. Upload Build Files to S3
bash
Copy
Edit
aws s3 sync build/ s3://my-react-bucket-0621 --profile terraformuser
í·¹ Tear Down
To destroy all provisioned AWS resources:

bash
Copy
Edit
terraform destroy -auto-approve
í³Œ Notes
aws_s3_bucket_public_access_block is configured to allow public access.

CloudFront is used for HTTPS and global distribution.

All resources are deployed to the us-east-1 region.

This setup is for learning and demonstration; use best practices for production (e.g., custom domain, SSL certs, WAF).

âœï¸ Author
Obasaju Winner
LinkedIn | GitHub# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)
=======
# my-react-app
>>>>>>> b5a4d4c4cd1ef7ed31ef514875e91040796ba2a3
