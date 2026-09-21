# NEO Media 0.3.1 — Native C++ / Win64

Versão nativa do NEO Media para Windows x64, migrada para **C++17**.

## Status da compilação

A versão **0.3.1 foi compilada com sucesso em Windows x64 pelo GitHub Actions**.

O build validou como PE x64:

- `NEO-Media.exe`
- `NEO-Repair.exe`
- `bin/neo_video.exe`
- `bin/neo_audio.exe`
- `bin/ffmpeg.exe`
- `bin/ffprobe.exe`

Também foi gerado com sucesso o instalador **NEO-Media-Setup-0.3.1.exe**.

Workflow usado: `.github/workflows/build-native.yml`

Build validado: https://github.com/jogoiarexx-blip/new-media/actions/runs/35646822912

## Download do código-fonte

O pacote fonte está no próprio repositório:

**[NEO-Media-0.3.1-Native-Cpp.zip](./NEO-Media-0.3.1-Native-Cpp.zip)**

Os executáveis compilados e o instalador são gerados pelo workflow Windows x64 e publicados como artifacts do GitHub Actions.

## Arquitetura

- **NEO-Media.exe** — interface/launcher Win32 em C++17.
- **neo_video.exe** — motor nativo de vídeo, FFmpeg e SDL2.
- **neo_audio.exe** — motor nativo de áudio e rádio.
- **NEO-Repair.exe** — reparador nativo do FFmpeg.
- **codigo-fonte/neo_media** — shell desktop C++.
- **codigo-fonte/neo_video** — motor multimídia C++.
- **BUILD-WINDOWS-NATIVE.ps1** — build local no Windows.
- **.github/workflows/build-native.yml** — compilação Windows x64 automatizada.
- **codigo-fonte/installer.nsi** — instalador NSIS.

## Versão

**0.3.1**

A arquitetura principal não utiliza Python, Tkinter, CFFI ou sounddevice no runtime final.

## Build local

Quem quiser recompilar localmente pode extrair o pacote e executar `BUILD-WINDOWS-NATIVE.ps1` no Windows com MSYS2 em `C:\msys64`.

O GitHub Actions já faz essa compilação automaticamente em um runner Windows x64, então não é necessário possuir um compilador instalado apenas para baixar e usar os binários gerados.

## Correção do erro 0xc000007b

A versão 0.3.1 inclui a nova estrutura de reparo do FFmpeg e o pipeline de build valida os executáveis e DLLs Windows x64 antes da distribuição.

Isso evita publicar novamente componentes PE truncados/corrompidos como o `avcodec-63.dll` que provocava **ffprobe.exe - Imagem Incorreta / 0xc000007b**.
