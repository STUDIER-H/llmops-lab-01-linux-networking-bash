# 🧪 LAB 01: Fundamentos de Linux, Redes, Sockets, HTTP/2, gRPC & Bash

## 🎯 Objetivo do Lab
Este laboratório valida suas habilidades fundamentais de administração de sistemas Linux, redes e automação Bash. Você irá configurar um ambiente Linux de produção, automatizar o monitoramento de portas/sockets de rede e testar chamadas de protocolos HTTP/2 e gRPC.

---

## 📋 Pré-requisitos
- Ter concluído os cursos da Fase 0 (*Technical Support Fundamentals* - Google).
- Computador com Windows (WSL2 + Ubuntu 22.04 LTS) ou Linux nativo.

---

## 🛠️ O que você deve construir neste Lab:

### Etapa 1: Provisionamento & Shell Bash
1. Instale e configure o **Ubuntu 22.04 LTS** no WSL2.
2. Escreva um script Bash em `scripts/system_health.sh` que:
   - Verifique o uso de CPU, memória RAM e espaço em disco.
   - Liste as portas escutando no sistema (`netstat -tulpn` ou `ss -tulpn`).
   - Salve os relatórios formatados com timestamp em `/var/log/system_health.log`.

### Etapa 2: Redes, Firewall & Sockets
1. Configure o firewall `ufw` para permitir apenas tráfego nas portas `22 (SSH)`, `80 (HTTP)`, `443 (HTTPS)` e `8000 (FastAPI)`.
2. Escreva um script em Python `scripts/socket_server.py` que abra um socket TCP na porta `9000` e responda com a mensagem `{"status": "healthy", "service": "llmops-socket"}`.

### Etapa 3: Protocolos HTTP/2 e gRPC
1. Instale a ferramenta `grpcurl` e `curl`.
2. Faça uma requisição HTTP/2 cURL e compare os cabeçalhos com uma requisição HTTP/1.1.
3. Escreva um arquivo `proto/service.proto` definindo uma mensagem gRPC `InferenceRequest` e `InferenceResponse`.

---

## ✅ Critérios de Aceitação & Entrega
- [ ] Script `system_health.sh` executável sem erros.
- [ ] Regras ativas do UFW comprovadas por print ou log em `docs/ufw_status.txt`.
- [ ] Servidor de socket rodando na porta 9000 e respondendo a conexões netcat (`nc`).
- [ ] Definição do arquivo `.proto` válida e compilada sem warnings.
