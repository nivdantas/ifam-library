# IFAM-Library
Projeto desenvolvido em Java para a criação de um aplicativo mobile, consistindo em um aplicativo para a reserva de livros em uma biblioteca.

O projeto foi feito utilizando os conceitos de Java, Android e o banco de dados Firebase.

![IMG_20230118_032345](https://user-images.githubusercontent.com/102577086/213111307-f4fcf907-b465-4426-a546-5f5c15658d7d.jpg)

Sistemas de usuários separados em leitores e bibliotecários.
Possui sistemas de cadastros de livros, visualização de livros reservados.

![Screenshot_225](https://user-images.githubusercontent.com/102577086/213111983-df45af0a-96d0-44f2-b05a-ac922b4e735a.png) ![Screenshot_227](https://user-images.githubusercontent.com/102577086/213112469-f4714b5a-b646-42f5-9b91-ead832ea1810.png)

## Desenvolvimento local

Abra o projeto no Android Studio com um JDK 11 ou 17 e instale a plataforma Android 12L (API 32). Para executar o aplicativo, configure Firebase Authentication com o provedor de e-mail e senha, Realtime Database e Cloud Storage em um projeto Firebase de desenvolvimento. Para usar esse projeto, obtenha seu próprio `google-services.json` para o pacote `com.example.projetodisp` e coloque-o em `app/` apenas na sua cópia local.

Na raiz do repositório, execute:

```sh
./gradlew assembleDebug lintDebug testDebugUnitTest
./gradlew connectedDebugAndroidTest
```

O segundo comando exige um dispositivo ou emulador Android conectado. No Windows, use `gradlew.bat`.

## Perfis e acesso

O cadastro público cria contas de leitores. A interface de bibliotecário continua usando o campo `bibliotecario` do perfil para escolher qual catálogo abrir. A concessão desse papel deve ser feita por um administrador autorizado, e as regras do Firebase devem impedir que leitores alterem o próprio papel ou executem operações de bibliotecário diretamente no banco ou no Storage.

Se uma instalação anterior gravou o campo `senha` no Realtime Database, trate esses registros como credenciais expostas. Revise o acesso aos dados, remova os campos antigos e solicite a redefinição das senhas afetadas.
