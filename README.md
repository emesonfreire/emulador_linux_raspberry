# emulador_linux_raspberry


https://forums.raspberrypi.com/viewtopic.php?t=36857


https://sourceforge.net/projects/rpiqemuwindows/

Raspberry Pi - emulador para Windows
Tue Mar 12, 2013 4:35 am

Emulando o Raspberry Pi no Windows

Para quem esta interessado em testar e sentir o gosto da Framboesa (Raspberry em inglês)
vou disponibilizar os procedimentos para emulação do Raspberry Pi no Windows.

O emulador usado é o QEMU. Não o conhecia, mais fiquei impressionado em saber a quantidade de processadores que ele pode simular.
http://wiki.qemu.org/Main_Page

Fiz um teste no Windows 7 e no Windows 8 e funcionou muito bem.
Veja que é um emulador (isto é um simulador) do Raspberry Pi que pode ser rodado no Windows.
Fica um pouco mais lento que o original, mas dá para se ter uma idéia de como funciona.

Você conseguirá rodar comandos em uma janela de terminal ou usar a janela gráfica (GUI). É claro que tem limitações e alguns programas podem não funcionar.

Primeiramente faça o download desse arquivo zipado (qemu.zip - 505 MB).
http://sourceforge.net/projects/rpiqemu ... t/download

Crie um diretório de teste no Windows e descompacte esse arquivo zipado nele.
(Dentro desse diretório terá o emulador QEMU e uma imagem do Raspbian - versão Debian do Linux para Raspberry Pi).
Imagem do Raspbian= 2012-07-15-wheezy-raspbian
A pasta deverá ter aproximadamente 2GB descompactados.

Dentro do diretório QEMU , rode a bat run.bat e deverá aparecer uma janela com o emulador QEMU rodando o Raspian.

Após alguns segundos de inicialização, deverá aparecer a janela de configuração inicial do Raspian.
Essa janela raspi-config só aparecerá no primeiro boot. Nela são feitas algumas configurações de memória, file system, teclado, relógio, etc. Para sair dela, se não desejar fazer nenhuma alteração, use a seta para baixo e a tecla tab para terminar (finish). Se for necessário faça as alterações para o seu teclado em português. Lembrando que o comando raspi-config poderá ser executado posteriormente em qualquer momento.

Se você pulou a configuração e rebootou o Raspberry, deverá pedir usuário(pi) e senha(raspberry).
O prompt de comando aparecerá pi@raspberry ~ $
Use as teclas CRTL e ALT para sair da janela de emulação, se precisar.

Para usar os comandos de Linux, é só digitá-los no prompt. Importante saber que você esta logado como usuário pi e não o root. Se quiser usar comandos com a autoridade de root, deverá acrescentar na frente do comando a palavra sudo. Por exemplo sudo reboot ou sudo halt.

Para inicializar a janela gráfica (GUI) dê o comando startx. Demora um pouquinho e aparecerá a janela.

Dentro do GUI, pode acessar Scratch(programação para crianças) , IDLE (python) Midori (web browser) e LXTerminal (janela de terminal).

Para dar logof, clique no botão vermelho na parte inferior 'a direita.

Essa imagem do Raspbian já esta desatualizada.Se quiser uma imagem mais atual (2013-02-09-wheezy-raspbian.zip) ou fazer teste com outras versões de linux acesse o link e faça o download no diretório QEMU.
link para download: http://www.raspberrypi.org/downloads

Mas para mudar a imagem, edite a bat run.bat que esta no diretório do Raspbian e troque o nome da imagem>
qemu-system-arm.exe -M versatilepb -cpu arm1176 -hda 2012-07-15-wheezy-raspbian.img -kernel kernel-qemu -m 192 -append

"root=/dev/sda2"

Bom proveito,

Gustavo Murta (Brasil)
