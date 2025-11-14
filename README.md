# Arquitetura SaaS para PDV

```mermaid
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
        MS1[ms-authorization]
        MS2[ms-users]
        MS3[ms-clients]
        MS4[ms-sales]
        MS5[ms-products]
        MS6[ms-stock]
        MS7[ms-payments]
        MS8[ms-finance]
        MS9[ms-reports]
        MS10[ms-integration]
        MS11[ms-notifications]
        MS12[ms-audit]
        MS13[ms-security]
        MS14[ms-monitoring]
    end

    MS --> GW_IaaS
    GW_IaaS[Gateway IaaS\nOrquestra tráfego para infraestrutura\n(rede, storage, banco, segurança)] --> AWS

    subgraph AWS [Infraestrutura AWS (IaaS/PaaS)]
        AWS1[EC2/EKS (Compute)]
        AWS2[S3 (Storage)]
        AWS3[RDS/DynamoDB (Banco de Dados)]
        AWS4[IAM/WAF (Segurança)]
        AWS5[CloudWatch (Monitoramento)]
        AWS6[Lambda (Serverless)]
    end
