
Ao executar o `npm install` de alguma codigo que você baixou, a mensagem de erro relativa ao `node-gyp` aparece:

> C:\...>node "C:\Program Files\nodejs\node_modules\npm\ bin\node-gyp-bin\\..\..\node_modules\node-gyp\bin\node-gyp.js" rebuild
Compilando os projetos desta solução um de cada vez. Para habilitar a compilação paralela, adicione a opção "/m".

> MSBUILD : error MSB3428: Não foi possível carregar componente "VCBuild.exe" do Visual C++.
Para corrigir isso, 1) instale o .NET Framework 2.0 SDK, 2) instale o Microsoft Visual Studio 2005 ou 3) adicione
o local do componente ao caminho do sistema se ele estiver instalado em outro local.

# Solução

https://github.com/nodejs/node-gyp/issues/629#issuecomment-153196245

Os passos de configuração sao os seguintes:

- Baixe o [VC++ Build Tools Technical Preview](http://go.microsoft.com/fwlink/?LinkId=691132).
- Na instalação, *não* siga direto: escolha *Custom Install* e, em seguida, selecione tanto as SDKs *Windows 8.1* quanto *Windows 10*.
  - Se, e *somente se*, você estiver no *Windows 7*, instale também o [.NET Framework 4.5.1](http://www.microsoft.com/en-us/download/details.aspx?id=40773)

- Instale o [Python 2.7](https://www.python.org/downloads/), e o adicione no seu `PATH`, `npm config set python python2.7`
  - Não instale o Python 3.*, não vai funcionar! Tem que ser 2.7.*!

Launch cmd, npm config set msvs_version 2015 --global (this is instead of npm install [package name] --msvs_version=2015 every time.)
SO MUCH npm install 