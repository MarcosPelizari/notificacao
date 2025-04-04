# API de Notificações

## Descrição
A API de Notificações é uma aplicação Java com Spring Boot que gerencia o envio de emails como notificações. Ela utiliza o Spring Mail para enviar emails via SMTP (Gmail) e o Thymeleaf para templates de email, permitindo o envio de notificações com base em dados de tarefas.

## Pré-requisitos
- **Java**: 17 ou superior
- **Gradle**: 8.x (usado para gerenciar dependências)
- **IntelliJ IDEA** (opcional, recomendado para desenvolvimento)
- **Postman** (recomendado para testar os endpoints)
- **Conta Gmail**: Necessária para configurar o envio de emails via SMTP.

## Instalação
1. **Clone o Repositório**:
   ```bash
   git clone https://github.com/seu-usuario/notificacao.git
   cd notificacao

2. **Configure as Credenciais de Email**:

  - Abra o arquivo src/main/resources/application.yml.
  - Adicione as credenciais do Gmail (username e password) e o remetente:

```yaml
  spring:
    mail:
        host: smtp.gmail.com
        port: 587
        username: seu.email@gmail.com
        password: sua-senha-de-app
        protocol: smtp
        properties:
            mail:
                smtp:
                    socketFactory:
                        port: 465
                        class: javax.net.ssl.SSLSocketFactory
                        fallback: false
                    auth: true
                    starttls: 
                        enable: true
                    connectiontimeout: 5000
                    timeout: 3000
                    writetimeout: 5000
    thymeleaf:
        enable: true

envio:
    email:
        remetente: seu.email@gmail.com
        nomeRemetente: 'Javanauta'

server:
  port: 8082
```

- Nota: Para o **password**, use uma senha de aplicativo do Gmail (não a senha normal). Para gerar uma senha de aplicativo:
  - Acesse sua conta Google > Segurança > Verificação em duas etapas (ative, se necessário) > Senhas de aplicativo > Gere uma senha para "Mail" no dispositivo "Custom".





