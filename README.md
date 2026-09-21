# NEO Media 0.3.1 — Native C++ / Win64

Versão nativa do NEO Media para Windows x64, migrada para **C++17**.

## Download do projeto completo

O pacote completo desta versão está no próprio repositório:

**[NEO-Media-0.3.1-Native-Cpp.zip](./NEO-Media-0.3.1-Native-Cpp.zip)**

O ZIP contém o código-fonte, scripts de build, workflow do GitHub Actions, instalador NSIS, documentação e os arquivos distribuídos com esta versão.

## Arquitetura

- **NEO-Media.exe** — interface/launcher Win32 em C++17.
- **neo_video.exe** — motor nativo de vídeo, FFmpeg e SDL2.
- **neo_audio.exe** — motor nativo de áudio e rádio.
- **NEO-Repair.exe** — reparador nativo do FFmpeg.
- **codigo-fonte/neo_media** — shell desktop C++.
- **codigo-fonte/neo_video** — motor multimídia C++.
- **BUILD-WINDOWS-NATIVE.ps1** — build local para Windows.
- **.github/workflows/build-windows-native.yml** — build Windows x64 automatizado.
- **codigo-fonte/installer.nsi** — instalador NSIS.

## Versão

**0.3.1**

Esta versão remove o runtime Python/Tkinter da nova arquitetura principal. O objetivo do pacote nativo é funcionar em C++/Win64, sem depender de Python instalado no computador.

## Compilação

Extraia o ZIP e execute `BUILD-WINDOWS-NATIVE.ps1` no Windows com MSYS2 instalado em `C:\msys64`.

O build gera a distribuição em `dist-native`.

## Correção do erro 0xc000007b

A versão 0.3.1 inclui a nova estrutura de reparo do FFmpeg para evitar o problema de DLL truncada/corrompida que causava o erro **ffprobe.exe - Imagem Incorreta / 0xc000007b**.
