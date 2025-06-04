You are a senior full-stack architect and AI-powered code generator. Build a modular microservices-based web application system that consists of:

1. **Admin Website** for creating, updating, previewing, deleting documentation.
   - Built using React (React Compiler preferred), React Router (custom router using browser API), React Query, TailwindCSS, Context + Redux if needed.
   - Docusaurus-based page rendering engine.
   - Role-based protected routes: Admin, Ops, Developer.
   - Pages: Login, Forgot Password, Invite to Join, Guarded Admin Panel (docs management), Blog Creation.
   - Only Admin can delete docs.
   - Tailwind theme customization using config and directives only (no UI libraries).

2. **Public Website** for viewing documentation and blogs.
   - Uses same Docusaurus output.
   - Public routes only.
   - Blog display section.
   - Client-side caching (browser) using service worker or React Query cache.

3. **Auth Server**:
   - Written in **Go**.
   - Features: Signup via invite, email + code based onboarding, login, forgot password, JWT-based role token.
   - Role-based access control (RBAC).
   - Exposes REST API.

4. **Backend Server**:
   - Written in **Go**.
   - Responsible for:
     - Documentation CRUD.
     - Blog CRUD.
     - Role-restricted fetch access.
     - Caching with Redis.
     - Vector/embedding-based storage (for semantic search).
   - DB: Use PostgreSQL (or other best-suited DB), managed via GORM or Ent ORM.

5. **Python Help Bot Server**:
   - Accepts user prompts and retrieves relevant docs using vector search.
   - Uses sentence-transformer or OpenAI embedding models.
   - Searches vector DB or pre-embedded documents.
   - Exposes minimal REST API `/ask?query=...`.

6. **Deployment**:
   - Each service has its own `Dockerfile`.
   - All services orchestrated via `docker-compose.yml`.

7. **Embedding + Vector Store**:
   - Store all docs/blogs with embeddings (during creation/update).
   - Use Pinecone, Qdrant, or Postgres + pgvector.
   - Backend Go server is responsible for generating and storing embeddings.

---

### ✍ Prompt Format to Use with AI

Here’s how to ask AI to generate each part:

---

#### 🧱 1. Project Scaffolding

```txt
Generate file/folder structure for:
- React Admin panel (with routes: /admin, /admin/docs, /admin/blog, etc.)
- Public site (with blog and docs view)
- Auth server (Go)
- Docs API server (Go)
- Help Bot server (Python)

Use best practices for folder naming, microservice boundaries, and shared code.
