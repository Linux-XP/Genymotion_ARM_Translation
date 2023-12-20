​<h1 align="center">:rocket: Genymotion_ARM_Translation :rocket: </h1>

<p alinhar="centro">
<a href="https://github.com/m9rc0">
   <img src="https://img.shields.io/website-up-down-green-red/https/shields.io.svg?label=m9rc0">
</a>
<a href="https://github.com/m9rc0/Genymotion_ARM_Translation">
     <img src="https://img.shields.io/github/license/mashape/apistatus.svg">
</a>
</p>

## Tradução Genymotion

```
├── LICENÇA
├── README.md
└── pacote
     ├── Genymotion-ARM-Translation_for_4.4.zip
     ├── Genymotion-ARM-Translation_for_5.1.zip
     ├── Genymotion-ARM-Translation_for_6.0.zip
     ├── Genymotion-ARM-Translation_for_7.X.zip
     ├── Genymotion-ARM-Translation_for_8.0.zip
     └── Genymotion-ARM-Translation_for_9.0.zip
```

## Mapeamento de versão do Android

* [4.3](/package/Genymotion-ARM-Translation_for_4.3.zip)
* [4.4](/package/Genymotion-ARM-Translation_for_4.4.zip)
* [5.1](/package/Genymotion-ARM-Translation_for_5.1.zip)
* [6.0](/package/Genymotion-ARM-Translation_for_6.0.zip)
* [7.X](/package/Genymotion-ARM-Translation_for_7.X.zip)
* [8.0](/package/Genymotion-ARM-Translation_for_8.0.zip)
* [9.0](/package/Genymotion-ARM-Translation_for_9.0.zip)

## Genymotion Não é possível instalar a solução APK:

1. baixe Genymotion-ARM-Translation-for[v]
2. Irá baixar o kit de ferramentas arrastando e soltando diretamente no Genymotion,
3. Se falhar
```
   1. adb shell
   2. cd /cartão SD/Download/
   3. sh /system/bin/flash-archive.sh /sdcard/Download/Genymotion-ARM-Translation.zip
   4. reinicialização do adb
```
4. Reinicializando o emulador

## Instalar o Adb

```bash
   brew cask instalar ferramentas da plataforma Android
```

## Perguntas frequentes/solução de problemas

### O APK ainda não é instalado após a instalação da ferramenta ARM_Translation

Se você ainda estiver recebendo esta mensagem de erro, siga o guia:

```
   Ocorreu um erro ao implantar o arquivo.
   Isso provavelmente significa que o aplicativo contém código nativo ARM e seu dispositivo Genymotion não pode executar instruções ARM. Você deve construir seu código nativo para x86 ou instalar uma ferramenta de tradução ARM em seu dispositivo.
```

1. Verifique se você instalou ARM_Translation com sucesso.
  - Execute `getprop ro.product.cpu.abilist` através do shell ADB. Se mostrar `x86,armeabi-v7a,armeabi`, ARM_Translation foi instalado com sucesso.
  - Se você não sabe como executar o shell ADB, siga [este guia](https://docs.genymotion.com/desktop/041_Deploying_an_app/#install-the-arm-translation-tools) para obter informações de ABI.

2. Verifique se armeabi-v7a é suficiente para o seu APK.
   - Execute `unzip -l YOUR_APP.apk | grep -o ' lib/[^/]*/' | único`. Se a saída **apenas** for `lib/arm64-v8a/`, significa que seu APK não suporta armv7 (32 bits). Você precisa de outra ferramenta de tradução armv8 (64 bits). [Este projeto](https://github.com/niizam/Genymotion_A11_libhoudini) pode ajudar.
