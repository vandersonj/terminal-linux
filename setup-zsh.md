# Personalizando o terminal do Linux

> Fonte: [Personalizado o terminal do linux](https://leovargas.notion.site/Personalizado-o-terminal-do-linux-b6703207388d4c78a7b505195a11ea6b)

## Antes de começar…

Atualize todos os pacotes do seu sistema operacional:

```bash
sudo apt update
sudo apt upgrade
```

## Instalando o ZSH

Por padrão o Linux vem com o terminal [bash](https://www.gnu.org/software/bash/), vamos substituir pelo zsh:

```bash
sudo apt install zsh
```

Configurar o terminal zsh como default. **OBS:** será necessário fazer um logout para salvar.

```bash
chsh -s $(which zsh)
```

## Instalando Oh My Zsh

O Oh My Zsh é um framework open source que possibilita o gerenciamento das configurações do interpretador de comandos Zsh. [Mais detalhes](https://ohmyz.sh/)

```bash
# pacotes necessários
sudo apt install curl git

sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Plugins do ZSH

### Instalando o zinit

Adicionando os plugins no zsh:

```bash
# Instalar zinit
bash -c "$(curl --fail --show-error --silent --location https://raw.githubusercontent.com/zdharma-continuum/zinit/HEAD/scripts/install.sh)"

# abrir o arquivo de configurações do zsh
code ~/.zshrc

# adicione no final do .zshrc
zinit light zdharma-continuum/fast-syntax-highlighting
zinit light zsh-users/zsh-autosuggestions
zinit light zsh-users/zsh-completions
```

### Explicando cada plugin

- **zsh-syntax-highlighting**
  O [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting) é utilizado para dar destaque aos comandos enquanto eles são digitados. Se o comando estiver correto, ele será exibido na cor verde, caso contrário, o comando ficará em vermelho. Isso ajuda a revisar os comandos antes de executá-los, principalmente na detecção de erros de sintaxe.

- **zsh-autosuggestions**
  O [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions) é extremamente útil para as pessoas desenvolvedoras, pois ele sugere comandos baseados nos comandos que já foram digitados anteriormente. Ele funciona como uma ferramenta para autocompletar o que está sendo digitado, nos poupando muito tempo.

- **zsh-completions**
  Seu objetivo é completar o comando e trazer informações sobre ele.

## Instalando fontes

### Nerd Fonts (ícones)

```bash
# criando diretório
mkdir ~/.fonts

# baixando fonte
wget -P ~/.fonts 'https://github.com/ryanoasis/nerd-fonts/releases/download/v3.4.0/BitstreamVeraSansMono.zip'

unzip ~/.fonts/BitstreamVeraSansMono.zip -d ~/.fonts
```

### Fira Code (fonte com ligatures)

```bash
sudo apt install fonts-firacode
```

### Como configurar a fonte no terminal

**PS:** será necessário fechar e abrir o terminal.

## Instalando o tema Powerlevel10k

```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git "${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k"

# abrir o arquivo de configurações do zsh
code ~/.zshrc

# alterar o valor do tema
ZSH_THEME="powerlevel10k/powerlevel10k"
```

Comando para configurar/reconfigurar o powerlevel10k:

```bash
p10k configure
```
