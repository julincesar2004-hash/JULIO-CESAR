Ir para o conteúdo
JULIO-CESAR
Navegação do repositório
Código
Problemas
Solicitações de pull
Ações
Projetos
✓ Windows Virtual PC
Configurar o Windows Virtual do PC nº 1
Arquivo de fluxo de trabalho para esta execução.
.github/workflows/blank.yml em 6cbbc48
Nome : Configurar PC Virtual Windows

sobre :
  workflow_dispatch :

empregos :
  configurar :
    executa em : windows-latest

    passos :
      - nome : Informações do sistema
        shell : powershell
        executar : |
          Write-Host "=== PC VIRTUAL ===" -ForegroundColor Verde
          Write-Host "Computador: $env:COMPUTERNAME"
          Write-Host "Usuário: $env:USERNAME"
          Obter informações do computador |
            Selecione o objeto WindowsProductName, WindowsVersion
      - nome : Verificar RDP
        shell : powershell
        executar : |
          Write-Host "Verificando Área de Trabalho Remota..."
          Get-Service TermService |
            Status do objeto selecionado, StartType
      - nome : Verificar rede
        shell : powershell
        executar : |
          Write-Host "=== CONFIGURAÇÃO DE REDE ==="
          Get-NetIPAddress -AddressFamily IPv4 |
            Where-Object {$_.IPAddress -notlike "127.*"} |
            Selecione o objeto IPAddress, InterfaceAlias
