# ShopNest on Replit

This is the imported React (Create React App), Express, and MongoDB app. Keep its existing `frontend/` and `backend/` structure and stack.

## Run

- Install the existing dependencies with `npm run install-all` from the project root.
- Press Run to start the `ShopNest` workflow, or run `npm run dev`.
- React listens on `0.0.0.0:5000`. Its development proxy forwards relative `/api` requests to Express on port 3001.
- The development server allows Replit's proxied hostnames; do not use that development server for production.
- The API connects to MongoDB before listening.

## Required secrets

Set `MONGO_URI` and `JWT_SECRET` through Replit Secrets. Never commit their values. For MongoDB Atlas, configure database-user permissions and network access for the environment.

## Optional services

- Product-image uploads: `CLOUDINARY_CLOUD_NAME`, `CLOUDINARY_API_KEY`, `CLOUDINARY_API_SECRET`.
- Razorpay: `RAZORPAY_KEY_ID`, `RAZORPAY_KEY_SECRET`.
- Email: `GMAIL_USER`, `GMAIL_PASS` (an app password).

These services are not required to start the app but their related operations need valid credentials. The imported checkout includes a test-order bypass; do not treat it as production payment verification.

## Data safety

Do not run `npm run seed` on an existing database without explicit permission: it deletes users and products and creates an admin with a publicly documented password. An empty database will show no products until they are added.

## Production build

`npm run build` builds the frontend. With `NODE_ENV=production`, `npm start` uses the existing Express static hosting on port 5000. Publishing and production hardening are separate from this development setup.