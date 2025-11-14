flowchart TD
    subgraph Frontend [Frontend (Flutter)]
        A[Android App]
        B[iOS App]
        C[Web (PDV, Dashboard)]
    end

    A --> BFF
    B --> BFF
    C --> BFF

    BFF[BFF (Backend for Frontend - Spring)\nAdapta APIs para cada tipo de cliente] --> GBL
    GBL[Gateway Business Layer (Spring)\nRegras de negócio, segurança, orquestração] --> MS

    subgraph MS [Microsserviços (Spring Boot)]
        MS1[ms-authorization\nAutenticação, login, permissões]
        MS2[ms-users\nGestão de usuários e perfis]
        MS3[ms-clients\nCadastro de clientes, fidelidade]
        MS4[ms-sales\nVendas PDV, NFC-e, promoções]
        MS5[ms-products\nCatálogo de produtos]
        MS6[ms-stock\nControle de estoque, inventário]
        MS7[ms-payments\nIntegração com meios de pagamento]
        MS8[ms-finance\nFluxo de caixa, contas, bancos]
        MS9[ms-reports\nRelatórios, BI, dashboards]
        MS10[ms-integration\nSEFAZ, ERP, sistemas externos]
        MS11[ms-notifications\nAlertas, push, e-mails]
        MS12[ms-audit\nAuditoria e logs]
        MS13[ms-security\nProteção contra fraudes]
        MS14[ms-monitoring\nMétricas e observabilidade]
    end

    MS --> GW_IaaS
    GW_IaaS[Gateway IaaS\nOrquestra tráfego para infraestrutura\n(rede, storage, banco, segurança)] --> AWS

    subgraph AWS [Infraestrutura AWS (IaaS/PaaS)]
        AWS1[EC2/EKS (Compute)]
        AWS2[S3 (Storage)\nNotas, documentos]
        AWS3[RDS/DynamoDB\nDados PDV]
        AWS4[IAM/WAF\nSegurança]
        AWS5[CloudWatch (Monitoramento)]
        AWS6[Lambda (Serverless)]
    end
