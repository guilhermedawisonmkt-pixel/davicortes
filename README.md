# CPlay | Presença Digital Local

Landing page em React/Vite para a CPlay, com conteúdo estático e assets públicos versionados.

## Desenvolvimento e validação

- `pnpm install --frozen-lockfile`: instala exatamente as versões do lockfile.
- `pnpm dev:static`: inicia a prévia estática na porta `3000`.
- `pnpm check`: valida os tipos TypeScript.
- `pnpm test`: executa os testes disponíveis.
- `pnpm build:static`: gera a versão estática em `dist/public`.

## Deploy na Vercel

O arquivo `vercel.json` já define a configuração recomendada:

- Install command: `pnpm install --frozen-lockfile`
- Build command: `pnpm build:static`
- Output directory: `dist/public`
- Framework preset: Vite

O projeto não precisa de servidor Express, banco de dados ou variáveis de ambiente para esta landing page. O número do WhatsApp continua centralizado em `client/src/config/site.ts`; enquanto estiver vazio, o CTA não cria um link fictício.

## GitHub

Versione o repositório incluindo `package.json`, `pnpm-lock.yaml`, `vercel.json`, `client/`, `docs/` e os demais arquivos-fonte. Não versionar `.env*`, `node_modules/`, `dist/` ou logs.

## Estrutura importante

- `client/src/pages/Home.tsx`: conteúdo e comportamento da landing page.
- `client/src/index.css`: tokens de cor e layout responsivo.
- `client/src/config/site.ts`: logo, marca e contato.
- `client/public/assets/`: logo oficial da CPlay.
- `client/public/manus-routes.json`: manifesto da rota principal.
- `docs/display-references.md`: referências usadas para os visuais dos displays.

O starter original também mantém scripts de Express, tRPC e Drizzle para compatibilidade com o template, mas a configuração da Vercel usa exclusivamente o build estático da landing page.
