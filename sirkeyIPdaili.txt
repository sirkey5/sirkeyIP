function FindProxyForURL(url, host) {
    var proxyServer = "PROXY 192.168.1.6:10808";
    var local = "DIRECT";

    // 测试代理服务器的连接性
    var proxyTestURL = "http://example.com/test";
    if (isInNet(dnsResolve(proxyTestURL), "0.0.0.0", "255.255.255.255")) {
        return proxyServer;
    }

    // 若代理服务器不可用，则使用本地网络
    return local;
}
