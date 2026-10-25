# Resonance – port para Minecraft 1.21.1 (NeoForge 21.1.x)

Base: código do `main` do repositório TalonFloof/Resonance (26.1.2, versão 0.1.2), adaptado para 1.21.1.
Somente NeoForge (o módulo `fabric/` foi removido).

## Como compilar
1. Instale o JDK 21.
2. Na pasta do projeto:  `./gradlew :neoforge:build`   (Windows: `gradlew.bat :neoforge:build`)
3. O .jar sai em `neoforge/build/libs/` (use o que NÃO termina em -sources/-javadoc).
4. Coloque na pasta `mods` junto com: NeoForge 21.1.x, **Fzzy Config 0.7.5+1.21 (NeoForge)**.
   Opcional: Serene Seasons 10.1.0.3 (NeoForge 1.21.1) + GlitchCore.

## O que mudou em relação ao código original
- Java 25 -> 21; Minecraft 26.1.2 -> 1.21.1; NeoForm 1.21.1-20240808.144430; NeoForge 21.1.249
- `Identifier` -> `ResourceLocation`
- `Level#getOverworldClockTime()` -> `Level#getDayTime()`
- `world.entity.npc.villager.Villager` -> `world.entity.npc.Villager`
- `SpreadingSnowyBlock(Properties, ResourceKey)` -> `SpreadingSnowyDirtBlock(Properties)` (GrassBlockMixin)
- `Level#playPlayerSound` (não existe na 1.21.1) -> `Constants.playPlayerSound` (EntityBoundSoundInstance)
- `Level#getHeight(Types, BlockPos)` -> `getHeight(Types, x, z)`
- `FMLLoader.getCurrent().isProduction()` -> `FMLEnvironment.production`
- Removidos imports não usados (NeoForgeBiomeTagsProvider, ClientPlayerNetworkEvent, Registrar)
- Removido o `refmap` do resonance.mixins.json e o accesswidener (só valem no Fabric)
- Dependências: Fzzy Config 0.7.5+1.21+neoforge, Serene Seasons (Modrinth ID SPj5bJoM), GlitchCore 1.21.1-2.1.0.0 (só runClient)

Licença do mod: LGPL-3.0-or-later (veja LICENSE.md e ATTRIBUTION.md).
