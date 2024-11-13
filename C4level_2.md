[![](https://mermaid.ink/img/pako:eNqFU81u00AQfpXRnlLJRT1wyi1OSAUqqGAQEvJlbI_TVe0da3-KkqoPgzj0CXiCvBjjnyR2hMLJu-v5fuab3WeVc0FqrpZvl2w8akM2NV77iuB4ACuNG4s1lGzhKz7S9eL6NuiCUhNzMAXa7Sy7iSBV459wX6EXRJ2qK3hOzZFu9s2RTcg-6ZyiVLU7-Khzy64_S1VL9QGfMIKksdpsIGb2_fGpcP_K0KBFCC7sf1nN7o0ojXWysmwhnUC8Xl_kjTF_7PpbW8FDgYBNpXPcv-5_8xnvBj21mMX9e7iV9U_cConsvyeQjHsYfl5mw12wPV27gHUwudds3EW7xyoIXld6hwU6aKhiGEKELLip0CqbrdBjhm6klny-6yzL1Dvedn-o6k8WtsYdGZQmCnYgcz3mHcEmaJSP52AdEHiLxrVN_qHzYYj6kl3dglLVr1Zxr_CJ_68q3ZWnYIT4JTVfqJpcJRjmLZqUe4mcYTrVDtiihshPht653GqBEFSkfZBLJX120ueYiaDkNaQdh1NlZ-NwR0ZmJtfl6h_-x-O5G3wQ0OBt4khFqibJSBfyduVxgUD8A9US31yWBZUYKmlYgpJSDJ6TrcnV3NtAkbIcNg9qXmIlYio0hbga3vihpEHzg7keil7-AokEcdE?type=png)](https://mermaid.live/edit#pako:eNqFU81u00AQfpXRnlLJRT1wyi1OSAUqqGAQEvJlbI_TVe0da3-KkqoPgzj0CXiCvBjjnyR2hMLJu-v5fuab3WeVc0FqrpZvl2w8akM2NV77iuB4ACuNG4s1lGzhKz7S9eL6NuiCUhNzMAXa7Sy7iSBV459wX6EXRJ2qK3hOzZFu9s2RTcg-6ZyiVLU7-Khzy64_S1VL9QGfMIKksdpsIGb2_fGpcP_K0KBFCC7sf1nN7o0ojXWysmwhnUC8Xl_kjTF_7PpbW8FDgYBNpXPcv-5_8xnvBj21mMX9e7iV9U_cConsvyeQjHsYfl5mw12wPV27gHUwudds3EW7xyoIXld6hwU6aKhiGEKELLip0CqbrdBjhm6klny-6yzL1Dvedn-o6k8WtsYdGZQmCnYgcz3mHcEmaJSP52AdEHiLxrVN_qHzYYj6kl3dglLVr1Zxr_CJ_68q3ZWnYIT4JTVfqJpcJRjmLZqUe4mcYTrVDtiihshPht653GqBEFSkfZBLJX120ueYiaDkNaQdh1NlZ-NwR0ZmJtfl6h_-x-O5G3wQ0OBt4khFqibJSBfyduVxgUD8A9US31yWBZUYKmlYgpJSDJ6TrcnV3NtAkbIcNg9qXmIlYio0hbga3vihpEHzg7keil7-AokEcdE)

C4Container
    title Container Diagram for Take-A-Guide

    Boundary(b0, "Take-A-Guide Platform") {
        Container(UserService,"User Microservice", "Java, Spring Boot", "Microserviço para usuários.")
        Container(bff, "User BFF", "Java, Spring Boot", "Back for Front da aplicação")
        Container(gate, "API Gateway","AWS Service", "Gateway da aplicação")
        Container(azure, "Azure Functions", "Java, Spring Boot", "Functions utilizadas pelo service bus")
        ContainerDb(Database, "Azure SQL Server", "SQL Database", "Armazena dados de usuários, guias, tours e transações.")
        ContainerDb(Cosmos, "CosmosDB", "NoSQL Database", "Armazena dados das functions")
        
    }
    Rel(UserService, bff, "Conecta ao Back for Front")
    Rel(azure, Cosmos, "Escrita e leitura de dados")
    Rel(azure,UserService, "Service Bus")
    Rel(bff, gate, "Conecta ao API Gateway")
    Rel(UserService, Database, "Leitura e escrita de dados")
