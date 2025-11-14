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
