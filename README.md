# Fluid Player para Android

Aplicativo Android **Fluid Player**, em modo **local + online**, que incorpora a interface Fluid Player HTML5 em uma WebView. O pacote Android usa `com.fluidplayer.android` e requer Android 6.0 (API 23) ou superior.

## Recursos

- Selecionar e reproduzir arquivos de vídeo do aparelho pelo seletor nativo do Android.
- Reproduzir links diretos HTTP/HTTPS de arquivos e streams compatíveis com Android WebView.
- Controles de vídeo em tela cheia.
- Interface em português.
- Player HTML5 como alternativa caso a CDN do Fluid Player não esteja acessível.

## Gerar o APK automaticamente

1. Abra a aba **Actions** deste repositório.
2. Selecione **Build Android APK** (ou aguarde a compilação disparada pelo push para `main`).
3. Abra a execução mais recente após ela terminar com sucesso.
4. Na seção **Artifacts**, baixe `Fluid-Player-Android-APK`.
5. Extraia `Fluid-Player.apk` do ZIP e abra-o no Android para instalar. Pode ser necessário permitir instalações pelo navegador ou gerenciador de arquivos.

O workflow usa JDK 17, Gradle 8.9 e Android SDK Platform 35. O Gradle 8.9 atende ao requisito mínimo do Android Gradle Plugin 8.7.3.

## Compilação local

Requer JDK 17, Gradle 8.9 e Android SDK Platform 35 / Build Tools 35.0.0. Na raiz do projeto:

```bash
gradle --no-daemon clean assembleDebug
```

O APK debug ficará em `app/build/outputs/apk/debug/app-debug.apk`.

## Limitações e segurança

- Esta é uma integração WebView, não um player Android nativo independente.
- A interface oficial Fluid Player é carregada da CDN `https://cdn.fluidplayer.com/v3/current/fluidplayer.min.js`; os controles Fluid Player exigem internet na primeira carga. O vídeo HTML5 pode funcionar como alternativa.
- Codecs e formatos dependem do Android WebView e do aparelho.
- Use links diretos de mídia. Páginas de sites, DRM, autenticação ou restrições contra reprodução externa podem impedir a reprodução. O aplicativo não contorna DRM ou bloqueios.
- O aplicativo aceita HTTP e HTTPS por compatibilidade. Prefira HTTPS e fontes confiáveis.
- O workflow gera um APK **debug** para testes, não um pacote de release assinado para Play Store.

## Projeto original

Fluid Player: https://github.com/fluid-player/fluid-player (licença MIT). Este repositório contém uma integração Android independente.
