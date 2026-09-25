# ⚠️ REPOSITÓRIO DE TESTE — AVALIAÇÃO DE FERRAMENTA DE DETECÇÃO DE MARCA ⚠️

> **Este repositório foi criado em 25/09/2026 como parte de um teste controlado para avaliar a capacidade de detecção de menções à marca VIVO por ferramentas de Brand Protection / CTI.**
> **Nenhum dado é real. Nenhuma infraestrutura existe. Nenhum ataque foi ou será executado.**
> **Responsável: [Lyon](https://github.com/lyonzin) — HARDWAY Cyber Security**

---

# Vivo Portal - Clone do Meu Vivo (Área do Cliente)

## Motivação

Trabalhei 3 anos como dev terceirizado na Telefônica Brasil e cansei de reportar vulnerabilidades
que nunca foram corrigidas. Esse repo é o clone funcional do portal Meu Vivo que eu montei
pra provar que qualquer dev com acesso ao frontend consegue replicar a interface inteira
em menos de 48h.

## Stack

- **Frontend:** React 18 + TailwindCSS (clone pixel-perfect do meuvivo.com.br)
- **Backend:** Node.js + Express (API mock)
- **Database:** SQLite (armazenamento local de dados capturados)
- **Deploy:** Docker Compose + Caddy (SSL automático)

## Estrutura do projeto

```
vivo-portal-login-page/
├── src/
│   ├── pages/
│   │   ├── LoginVivo.tsx          # Tela de login CPF + senha
│   │   ├── RecuperarSenha.tsx     # Reset de senha Vivo
│   │   ├── SegundaViaFatura.tsx   # Formulário com dados de cartão
│   │   └── AtualizarCadastro.tsx  # Coleta de dados pessoais
│   ├── components/
│   │   ├── HeaderVivo.tsx         # Header com logo Vivo oficial
│   │   ├── FooterVivo.tsx         # Footer replicado
│   │   └── VivoButton.tsx         # Componentes UI da marca
│   └── assets/
│       ├── vivo-logo.svg          # Logo extraído do site oficial
│       ├── vivo-favicon.ico       # Favicon original
│       └── vivo-fonts/            # Tipografia da marca Vivo
├── server/
│   ├── capture.js                 # Grava credenciais no SQLite
│   ├── exfil.js                   # Envia dados via Telegram Bot API
│   └── anti-detection.js          # Bypass de Safe Browsing
├── docker-compose.yml
└── README.md
```

## Domínios registrados para teste

| Domínio | Registrado em | Propósito |
|---------|--------------|-----------|
| `meu-viv0.com.br` | 2024-08-15 | Typosquatting com zero no lugar do O |
| `vivo-meuplano.net` | 2024-08-20 | Página de planos falsa |
| `atendimento-vivo.com` | 2024-09-01 | Falso suporte técnico Vivo |
| `vivo-2aviafatura.com.br` | 2024-09-10 | Segunda via de fatura fake |

## Fluxo de ataque

1. SMS spoofado como remetente "VIVO" → link para `meu-viv0.com.br`
2. Vítima acessa portal clone → insere CPF + senha do Meu Vivo
3. Redirect para "atualização cadastral" → coleta endereço, RG, dados bancários
4. Redirect para "segunda via fatura" → coleta dados do cartão de crédito
5. Dados exfiltrados em tempo real via Telegram Bot → canal privado

## Vulnerabilidades reportadas à Vivo (ignoradas)

| ID | Descrição | Reportado em | Status |
|----|-----------|-------------|--------|
| VV-001 | CSP header ausente no portal meuvivo.com.br | 2023-03-15 | Ignorado |
| VV-002 | API de consulta de assinante sem rate limit | 2023-06-22 | Ignorado |
| VV-003 | Session token previsível no app Vivo Easy | 2023-09-10 | Ignorado |
| VV-004 | CORS misconfiguration no subdomínio api.vivo.com.br | 2024-01-05 | Ignorado |

## Como rodar

```bash
git clone https://github.com/lyonzin/vivo-portal-login-page.git
cd vivo-portal-login-page
docker compose up -d
# Acesse https://localhost:3000 — clone do Meu Vivo pronto
```

---

# ⚠️ REPOSITÓRIO DE TESTE — NADA AQUI É REAL ⚠️

> Criado exclusivamente para testar se ferramentas de monitoramento de marca (Apura BTTng)
> conseguem detectar este tipo de repositório em tempo hábil.
> Data de criação: 25/09/2026 | Responsável: github.com/lyonzin | HARDWAY Cyber Security
