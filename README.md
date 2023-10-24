multi-v2ray
Script de gerenciamento multiusuário V2ray/Xray, protocolo de transmissão de gerenciamento baseado em assistente [adicionar | excluir | modificar]
 Transferências Transferências  

ChinêsInglês _
recurso
O mais importante sobre raio X, v2ray e raio
Chame a API oficial do v2ray para obter estatísticas de tráfego
 Gerenciamento multiusuário, multiporta e gerenciamento de protocolo de transmissão misto não é mais um sonho
Uma porta aleatória é gerada durante a primeira instalação. A configuração padrão é mkcp + uma camuflagem de cabeçalho aleatória (srtp | wechat-video | utp | dtls | wireguard); as informações de configuração são exibidas após a conclusão da instalação
 ;
Visualize as informações de configuração para exibir a string vmess/vless (formato de link de compartilhamento do v2rayN)
Gere link de compartilhamento de meias5/MTProto do Telegram , suporte para combinação de meias5 + tls
Suporta http/2, gera aleatoriamente caminho h2 falso
Ativar e desativar tcpFastOpen
Abra o CDN diretamente
Ativar e desativar portas dinâmicas
Atualize o v2ray regularmente (precisa ser ativado manualmente)
Suporta novo formato de arquivo de configuração v2ray (v4.1+)
Modificação da porta do intervalo de suporte
Programa de suporte e controle de gerenciamento de parâmetros de linha de comando
Suporte à implantação do docker
Suporta VLESS, Trojan e XTLS (v4.31.0+)
Suporta vps ipv6 puro
Sem BT
Função
Iniciar/parar/reiniciar o servidor V2ray com um clique
Estatísticas de tráfego (v2ray && iptables)
Gerenciamento de modo de linha de comando v2ray
Suporta gerenciamento multiusuário e multiportas
Ativar e desativar portas dinâmicas
Proibição e lançamento de Bittorrent
Porta única, modificação de porta de intervalo
Vá diretamente para Cloudcflare cdn
Ativar e desativar tcpFastOpen
Visualize rapidamente informações de conexão do servidor e faça modificações gerais na configuração
Altere livremente a configuração de transferência :
TCP normal
Mascaramento de cabeçalho HTTP
Tráfego WebSocket
Tráfego mKCP regular
mKCP disfarça o tráfego de chamadas FaceTime (srtp)
mKCP disfarça o tráfego de download de BT (utp)
mKCP disfarça o tráfego de videochamada WeChat (wechat-video)
mKCP disfarça o tráfego DTLS 1.2 (dtls)
mKCP disfarça o tráfego WireGuard (wireguard)
Tráfego HTTP/2 tls (h2) (nome de domínio obrigatório)
Meias5
MTProto
Meias Sombrias
Rápido
VLESS_TCP
VLESS_TLS
VLESS_WS
VLESS_REALITY
troiano
Comando de instalação
source <(curl -sL https://multi.netlify.app/v2ray.sh) --zh
Comando de atualização (manter o arquivo de configuração atualizado)
source <(curl -sL https://multi.netlify.app/v2ray.sh) -k
comando de desinstalação
source <(curl -sL https://multi.netlify.app/v2ray.sh) --remove
Parâmetros de linha de comando
v2ray/xray [-h|help] [options]
    -h, help             查看帮助
    -v, version          查看版本号
    start                启动 V2Ray
    stop                 停止 V2Ray
    restart              重启 V2Ray
    status               查看 V2Ray 运行状态
    new                  重建新的v2ray json配置文件
    update               更新 V2Ray 到最新Release版本
    update [version]     更新 V2Ray 到指定版本
    update.sh            更新 multi-v2ray 到最新版本
    add                  新增端口组
    add [protocol]       新增一种协议的组, 端口随机, 如 v2ray add utp 为新增utp协议
    del                  删除端口组
    info                 查看配置
    port                 修改端口
    tls                  修改tls
    tfo                  修改tcpFastOpen
    stream               修改传输协议
    cdn                  走cdn
    stats                v2ray流量统计
    iptables             iptables流量统计
    clean                清理日志
    log                  查看日志
    rm                   卸载core
Execução do Docker
Por padrão, mkcp + um arquivo de configuração de cabeçalho de camuflagem aleatório é criado ( se estiver usando xray, altere-o para o espelho jrohy/xray ):

docker run -d --name v2ray --privileged --restart always --network host jrohy/v2ray
Arquivo de configuração v2ray personalizado:

docker run -d --name v2ray --privileged -v /path/config.json:/etc/v2ray/config.json --restart always --network host jrohy/v2ray
Veja a configuração do v2ray:

docker exec v2ray bash -c "v2ray info"
aviso : Se você usa centos, você precisa primeiro desligar o firewall

systemctl stop firewalld.service
systemctl disable firewalld.service
sugestão
Depois de instalar o v2ray, é altamente recomendável ativar o BBR e outras acelerações: one_click_script
usa protocolos Trojan e VLESS.Recomenda-se instalar o nginx sozinho, o que pode fazer com que o v2ray retorne à porta 80 padrão sem problemas.

confiar
docker v2ray: https://hub.docker.com/r/jrohy/v2ray
docker xray: https://hub.docker.com/r/jrohy/xray
pip: https://pypi.org/project/v2ray- utilitário/
python3: https://github.com/Jrohy/python3-install
acme: https://github.com/acmesh-official/acme.sh
