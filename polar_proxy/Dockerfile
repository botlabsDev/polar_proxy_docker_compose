# syntax=docker/dockerfile:1

FROM mcr.microsoft.com/dotnet/core/runtime:2.2

RUN groupadd -g 31337 polarproxy &&\
    useradd -m -u 31337 -g polarproxy polarproxy &&\
    mkdir -p /var/log/PolarProxy /opt/polarproxy &&\
    chown polarproxy:polarproxy /var/log/PolarProxy &&\
    curl -s https://www.netresec.com/?download=PolarProxy | tar -xzf - -C /opt/polarproxy

USER polarproxy
WORKDIR /opt/polarproxy/
ENTRYPOINT ["dotnet", "PolarProxy.dll"]
CMD ["-v", "-p", "10443,80,443", "-o", "/polarproxy_pcaps/", "--certhttp", "10080", "--pcapoverip", "0.0.0.0:57012"]
