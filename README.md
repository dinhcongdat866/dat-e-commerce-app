## E-Commerce App (Next.js App Router)

Personal side project to build a full-featured e-commerce platform and demo practical Next.js 15 App Router patterns (auth, data fetching, state management, **`SSR` / `CSR`**, routing). Not a production e-commerce app.

### Core business data
- **Product**: id, name, price, image, isFavorite.
- **Cart**: items with quantity; add/remove/update operations.
- **Order**: order details (items, shipping address, payment method, delivery status); order history.
- **Profile**: user info (name, email, phone, image); saved addresses (CRUD); password management.

### Main features
- **Authentication**: Google OAuth via **`NextAuth`**; middleware guards protected routes; session management with server/client components.
- **Home**: Featured products showcase; hero section; **`SSR`** server component fetch; horizontal scroll product list.
- **Products**: Product listing page with **`SSR`**; product cards with add-to-cart and favorite buttons; responsive grid layout.
- **Product Details**: Individual product page with image gallery; quantity selector; add to cart; customer reviews; rating display.
- **Search**: Debounced autocomplete search (**`500ms`** delay); paginated results via **`/api/search`**; navigate to product on selection.
- **Cart**: Shopping cart management; item quantity updates; remove items; order summary calculation; **`Redux Toolkit`** state.
- **Checkout**: Shipping address form; payment method selection; order summary; order creation flow.
- **User Profile**: Profile editing (name, email, phone); password change dialog; saved addresses management (add/edit); order history list with status chips.
- **Order Details**: Order information display; delivery status tracking; shipping address; payment method; order items summary.
- **API & data layer**: Next.js **Route Handlers** under `/api/products` (GET) + `/api/search` (GET with pagination) + `/api/auth/[...nextauth]` (NextAuth); in-memory mock data.
- **Rendering & state**: **`Redux Toolkit`** for client-side state (cart, profile, orders); server components for **`SSR`** (home, products); client components for interactive UI (cart, checkout, profile, search).
- **UI/UX**: Material-UI (MUI) components; responsive design (mobile drawer menu); custom theme provider; snackbar notifications; loading states.
- **State management**: Redux slices for cart, products, order, orderDetails, orderHistory, profile; typed hooks (`useAppDispatch`, `useSelector`).

### Running locally
```bash
npm install
# or
pnpm install

npm run dev    # http://localhost:3000
# or
pnpm dev

npm run lint   # ESLint
# or
pnpm lint
```

**Environment variables** (`.env.local`):
```
NEXTAUTH_SECRET=your-secret-key
GOOGLE_CLIENT_ID=your-google-client-id
GOOGLE_CLIENT_SECRET=your-google-client-secret
```
