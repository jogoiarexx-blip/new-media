# NEO Media 0.3.1 Native C++

NEO Media é um reprodutor multimídia nativo para Windows x64, migrado para C++17.

## Estrutura
- `codigo-fonte/neo_media`: interface e launcher nativo.
- `codigo-fonte/neo_video`: motor de vídeo, áudio, filtros, hardware e telemetria.
- `.github/workflows/build-windows-native.yml`: build automático no GitHub Actions.
- `BUILD-WINDOWS-NATIVE.ps1`: build local no Windows.
- `codigo-fonte/installer.nsi`: instalador NSIS.

## Versão
0.3.1

A versão 0.3.1 remove o runtime Python da arquitetura principal e usa C++17/Win64.
