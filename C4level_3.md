[![](https://mermaid.ink/img/pako:eNqFVc1u00AQfpWRT0FK4cIpNychBQSlNEFIyFI1sSfuqvauuz-BturDVBwqca14grwYs_6r7ZTmlN35-775Zja-DWKVUDAJZm9nKi-UJGkjaYXNCFoDzAWmGnPYKA0rvKSj8OjYiYQiOVPSopCkz6fKyQT19chyQFi6w6IYQxR8M6SXpLcipih4Bbc-q648cuzzNbTKMtJNNDyZosAb24QJLAstZBrJqVIWzsjYZ4LLOybMVpPhRLO731IGBWUIKafsfitIlImkM253r4Uyr5nZkFfNuSXV9vAsI_CEItkLOiZNMhYICNnuMRUxQkIgKd09xgzqOcCLFM6oUEZYpa9bFk-mQ9L04zpcCtJGsAp_yrsnkWByiE5OxmBKHVE-V5YDutR0ekHv5JaBCQqtYl8EcpK-lDRenwGFu86WjdabjS8wXSyqSl3tS8MU40uSSbmqC815fIlkfw3YZTwdzVpgkfFYdg9-JeJMMHFqOm8wsRDHaOknlkMITz9Afa0Qw-_Lfne117fCwbxlV45AK0tefMMreeWEEQz5lwwUqBFY95LQ7oFPyKpwV34iAybz9Si8cboUvzzA8uunErtZfX-fo8U1mppMqHO8IYmRrGfc0XcMqRPIP1Y5bXgeViPPoWI2wD5_98uO0IMunIytYDWfaLSmmkXJKOPJRrJxVZ7TZuC0ZaWVx9w4WUvB1NbV9Pb7nimTKzOfVitWnauSJ-r_TVd7za1TZ8OoAa9Qzijb-xfae_3YC21dzz3RfmjX285uGNSFrhecTRRb3peqoY_LLydv3q9Wp8s2sQzsr-bhpOEjfrmBYfT--AeIHgxWWqSpX8i6yjCrO8oGLRgHOfHQRMKfIv5AAPvsBeU8zwkfE9qgy_iF878Bh6Kzankt42BitaNxoJVLL4LJBjPDN1ckLEn9yWqtBcofSjX3u39DfIFv?type=png)](https://mermaid.live/edit#pako:eNqFVc1u00AQfpWRT0FK4cIpNychBQSlNEFIyFI1sSfuqvauuz-BturDVBwqca14grwYs_6r7ZTmlN35-775Zja-DWKVUDAJZm9nKi-UJGkjaYXNCFoDzAWmGnPYKA0rvKSj8OjYiYQiOVPSopCkz6fKyQT19chyQFi6w6IYQxR8M6SXpLcipih4Bbc-q648cuzzNbTKMtJNNDyZosAb24QJLAstZBrJqVIWzsjYZ4LLOybMVpPhRLO731IGBWUIKafsfitIlImkM253r4Uyr5nZkFfNuSXV9vAsI_CEItkLOiZNMhYICNnuMRUxQkIgKd09xgzqOcCLFM6oUEZYpa9bFk-mQ9L04zpcCtJGsAp_yrsnkWByiE5OxmBKHVE-V5YDutR0ekHv5JaBCQqtYl8EcpK-lDRenwGFu86WjdabjS8wXSyqSl3tS8MU40uSSbmqC815fIlkfw3YZTwdzVpgkfFYdg9-JeJMMHFqOm8wsRDHaOknlkMITz9Afa0Qw-_Lfne117fCwbxlV45AK0tefMMreeWEEQz5lwwUqBFY95LQ7oFPyKpwV34iAybz9Si8cboUvzzA8uunErtZfX-fo8U1mppMqHO8IYmRrGfc0XcMqRPIP1Y5bXgeViPPoWI2wD5_98uO0IMunIytYDWfaLSmmkXJKOPJRrJxVZ7TZuC0ZaWVx9w4WUvB1NbV9Pb7nimTKzOfVitWnauSJ-r_TVd7za1TZ8OoAa9Qzijb-xfae_3YC21dzz3RfmjX285uGNSFrhecTRRb3peqoY_LLydv3q9Wp8s2sQzsr-bhpOEjfrmBYfT--AeIHgxWWqSpX8i6yjCrO8oGLRgHOfHQRMKfIv5AAPvsBeU8zwkfE9qgy_iF878Bh6Kzankt42BitaNxoJVLL4LJBjPDN1ckLEn9yWqtBcofSjX3u39DfIFv)

C4Component
    title Component Diagram for Take-A-Guide

    Container_Boundary(takeAGuideApp, "UserService") {

        Component(userController, "User Controller", "Component: Spring Boot Rest Controller", "Controlador responsável pela gestão dos usuários.")
        Component(userService, "User Service", "Component: Spring Boot Service", "Gerencia a lógica de negócios dos usuários.")
        Component(userRepository, "User Repository", "Component: Spring Boot Repository", "Gerencia a persistência dos dados dos usuários.")
        Component(messageService, "Message Service", "Component: Spring Boot Service", "Envia e processa mensagens de usuários.")
    }

    Container(bff, "BFF", "Spring Boot", "Backend for Frontend responsável por servir a aplicação cliente.")
    Container(apiGateway, "API Gateway", "AWS Service", "Gateway de APIs que roteia as requisições para os serviços apropriados.")
    ContainerDb(Azure, "Azure SQL Server", "SQL Database", "Armazena dados de usuários, guias, tours e transações.")
    
    Container_Ext(azureFunctions, "Azure Functions", "Serverless Function", "Processa eventos e funções de backend.")
    ContainerDb(CosmosDB, "CosmosDB", "NoSQL Database", "Armazena dados de mensagens e eventos.")

    Rel(userController, userService, "Usa")
    Rel(userService, userRepository, "Usa")
    Rel(userRepository, Azure, "Usa")
    Rel(userController, bff, "Conecta a", "JSON/HTTPS")
    Rel(bff, apiGateway, "Conecta a", "JSON/HTTPS")
    Rel(messageService, userRepository, "Usa")
    Rel(messageService, azureFunctions, "Conecta a", "HTTP Trigger")
    Rel(azureFunctions, CosmosDB, "Usa")
