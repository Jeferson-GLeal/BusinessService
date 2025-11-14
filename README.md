## Frontend (Flutter)
- Aplicações multiplataforma (Android, iOS e Web).
- Interface para PDV e dashboards de gestão.
- Único código reduz custo e acelera entregas.

## BFF (Backend for Frontend - Spring)
- Camada intermediária entre frontend e backend.
- Adapta APIs para cada tipo de cliente (mobile ou web).
- Simplifica comunicação e melhora performance.

## Gateway Business Layer (Spring)
- Centraliza regras de negócio.
- Aplica políticas de segurança.
- Orquestra chamadas entre microsserviços.

## Microsserviços (Spring Boot)
- **ms-authorization** → autenticação e permissões.
- **ms-users** → gestão de usuários.
- **ms-clients** → cadastro de clientes e fidelidade.
- **ms-sales** → vendas e emissão de notas fiscais.
- **ms-products** → catálogo de produtos.
- **ms-stock** → controle de estoque.
- **ms-payments** → integração com meios de pagamento.
- **ms-finance** → fluxo de caixa e contas.
- **ms-reports** → relatórios e BI.
- **ms-integration** → integração com SEFAZ e ERP.
- **ms-notifications** → alertas e e-mails.
- **ms-audit** → auditoria e logs.
- **ms-security** → proteção contra fraudes.
- **ms-monitoring** → métricas e observabilidade.

## Gateway IaaS
- Ponte entre microsserviços e infraestrutura.
- Orquestra tráfego e abstrai recursos da nuvem.
- Garante segurança e controle de rede.

## Infraestrutura AWS (IaaS/PaaS)
- **EC2/EKS** → execução e orquestração de containers.
- **S3** → armazenamento de documentos e notas.
- **RDS/DynamoDB** → bancos de dados relacionais e NoSQL.
- **IAM/WAF** → segurança e controle de acessos.
- **CloudWatch** → monitoramento.
- **Lambda** → funções serverless.


                                  ┌───────────────────────────┐
                                  │   Frontend (Flutter)      │
                                  └───────────────────────────┘
                                                │
                         ┌──────────────────────┼─────────────────────────┐
                         ▼                      ▼                         ▼
                 ┌───────────────────┐  ┌───────────────────┐ ┌───────────────────────┐
                 │   Android App     │  │     iOS App       │ │ Web (PDV, Dashboard)  │
                 └───────────────────┘  └───────────────────┘ └───────────────────────┘
                         │                      │                         │
                         └───────────┬──────────┴───────────┬─────────────┘
                                     ▼                      ▼
                          ┌─────────────────────────────────────────────┐
                          │   BFF (Backend for Frontend - Spring)       │
                          │   Adapta APIs para cada tipo de cliente     │
                          └─────────────────────────────────────────────┘
                                                │
                                                ▼
                         ┌──────────────────────────────────────────────┐
                         │  Gateway Business Layer (Spring)             │
                         │  Regras de negócio, segurança, orquestração  │
                         └──────────────────────────────────────────────┘
                                                │
                                                ▼
                  ┌─────────────────────────────────────────────────────────────┐
                  │                   Microsserviços (Spring Boot)              │
                  │ ┌─────────────────────────────────────────────────────────┐ │
                  │ │ ms-authorization   → autenticação, login, permissões    │ │
                  │ │ ms-users           → gestão de usuários e perfis        │ │
                  │ │ ms-clients         → cadastro de clientes, fidelidade   │ │
                  │ │ ms-sales           → vendas PDV, NFC-e, promoções       │ │
                  │ │ ms-products        → catálogo de produtos               │ │
                  │ │ ms-stock           → controle de estoque, inventário    │ │
                  │ │ ms-payments        → integração com meios de pagamento  │ │
                  │ │ ms-finance         → fluxo de caixa, contas, bancos     │ │
                  │ │ ms-reports         → relatórios, BI, dashboards         │ │
                  │ │ ms-integration     → SEFAZ, ERP, sistemas externos      │ │
                  │ │ ms-notifications   → alertas, push, e-mails             │ │
                  │ │ ms-audit           → auditoria e logs                   │ │
                  │ │ ms-security        → proteção contra fraudes            │ │
                  │ │ ms-monitoring      → métricas e observabilidade         │ │
                  │ └─────────────────────────────────────────────────────────┘ │
                  │   Segmentos atendidos: mercados, padarias, escolas,         │
                  │   depósitos de materiais, oficinas, funilarias, farmácias   │
                  └─────────────────────────────────────────────────────────────┘
                                               │
                                               ▼
                         ┌───────────────────────────────────────────┐
                         │            Gateway IaaS                   │
                         │   Orquestra tráfego para infraestrutura   │
                         │   (rede, storage, banco, segurança)       │
                         └───────────────────────────────────────────┘
                                               │
                                               ▼
                 ┌───────────────────────────────────────────────────────────────┐
                 │                Infraestrutura AWS (IaaS/PaaS)                 │
                 │ ┌───────────────┬───────────────┬───────────────┬───────────┐ │
                 │ │ EC2/EKS       │ S3 (Storage)  │ RDS/DynamoDB  │ IAM/WAF   │ │
                 │ │ (Compute)     │ (Notas, docs) │ (Dados PDV)   │ Segurança │ │
                 │ └───────────────┴───────────────┴───────────────┴───────────┘ │
                 │        CloudWatch (Monitoramento) / Lambda (Serverless)       │
                 └───────────────────────────────────────────────────────────────┘ 
