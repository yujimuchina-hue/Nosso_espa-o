# Nosso Cantinho

Um espaço privado para publicar, ler e escrever livros e fanfics (romance, fantasia, drama, dark romance, diário de um vampiro). Interface moderna em tons de azul, com leitor por capítulos, editor online e sistema de autenticação restrito.

## Funcionalidades principais
- Catálogo categorizado (romance, fantasia, drama, dark romance, diário de um vampiro)
- Pesquisa por título, autor e tags
- Leitura por capítulos com marcação do último capítulo lido
- Editor WYSIWYG para autores (rascunho, salvar, publicar capítulo)
- Sistema de autenticação e permissões (registro/login, níveis de author/reader/admin)
- Perfil de autor, comentários e avaliações
- Upload e gestão de capas e mídias
- Design responsivo com tema em tons de azul

## Stack sugerida
- Frontend: Next.js (React) + Tailwind CSS
- Backend: Node.js + Express ou Next.js API Routes
- Banco de dados: PostgreSQL (ou SQLite em desenvolvimento)
- Autenticação: NextAuth.js ou JWT + bcrypt
- Armazenamento de mídia: AWS S3 (ou armazenamento local em dev)
- ORM: Prisma ou Sequelize

## Instalação (exemplo monorepo)
1. git clone https://github.com/yujimuchina-hue/Nosso-Cantinho-.git
2. cd Nosso-Cantinho-
3. cp .env.example .env
4. npm install (ou yarn)
5. npm run dev

## .env.example
DATABASE_URL=postgresql://user:password@localhost:5432/nossocantinho  
NEXTAUTH_URL=http://localhost:3000  
JWT_SECRET=uma_chave_secreta_aqui  
S3_BUCKET_NAME=seu-bucket  
S3_REGION=regiao  
S3_ACCESS_KEY_ID=your_key  
S3_SECRET_ACCESS_KEY=your_secret

## Estrutura inicial sugerida
- /apps
  - /frontend (Next.js)
  - /backend (Express ou API do Next)
- /db
  - migrations/
  - seeds/
- /scripts
- .env.example
- README.md
- package.json (root com workspaces ou scripts de conveniência)
- LICENSE

## Modelos de dados (resumo)
- User: id, name, email, password_hash, role (reader/author/admin)
- Work: id, title, description, author_id, tags, cover_url, status (draft/published)
- Chapter: id, work_id, number, title, content, published_at
- Comment: id, user_id, chapter_id, content, created_at
- Rating: id, user_id, work_id, score

## Rotas/API (exemplo)
- POST /api/auth/register
- POST /api/auth/login
- GET /api/works?category=&search=
- GET /api/works/:id
- POST /api/works (autenticado: author)
- POST /api/works/:id/chapters (autenticado: author)
- GET /api/works/:id/chapters/:num

## Como contribuir
1. Crie uma branch feature/nome-da-funcionalidade  
2. Faça commits pequenos e descritivos  
3. Abra um Pull Request para main com descrição das mudanças  
4. Adicione testes quando aplicável

## Scripts úteis (exemplos)
- npm run dev (inicia frontend e backend em modo dev)  
- npm run build  
- npm run migrate  
- npm run seed

## Licença
MIT — veja LICENSE

## Contato
yujimuchina-hue (GitHub)