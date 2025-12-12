# 🔒 Permissões no Android

## 📘 Introdução

As **permissões** no Android são utilizadas quando o aplicativo precisa acessar **recursos sensíveis** ou **informações privadas** do dispositivo, como câmera, localização, armazenamento, contatos, etc.  

A partir do **Android 6.0 (API 23)**, as permissões passaram a ser solicitadas **em tempo de execução**, aumentando a segurança e o controle do usuário.

---

## 🧩 Tipos Comuns de Permissões

| Tipo | Descrição | Exemplo de Permissão |
|------|------------|----------------------|
| **Câmera** | Captura fotos ou vídeos | `android.permission.CAMERA` |
| **Localização** | Obtém a localização do dispositivo | `android.permission.ACCESS_FINE_LOCATION`, `android.permission.ACCESS_COARSE_LOCATION` |
| **Armazenamento** | Lê ou grava arquivos no armazenamento do dispositivo | `android.permission.READ_EXTERNAL_STORAGE`, `android.permission.WRITE_EXTERNAL_STORAGE` |
| **Internet** | Permite conexão à rede | `android.permission.INTERNET` |
| **Microfone** | Grava áudio | `android.permission.RECORD_AUDIO` |
| **Contatos** | Acessa a agenda de contatos do usuário | `android.permission.READ_CONTACTS` |
| **Bluetooth** | Comunicação com dispositivos via Bluetooth | `android.permission.BLUETOOTH`, `android.permission.BLUETOOTH_ADMIN` |
| **Câmera Frontal** | Captura selfies ou vídeos com a câmera frontal | `android.permission.CAMERA` |

---

## ⚙️ Permissões em Tempo de Execução

A partir do Android 6.0, **não basta declarar a permissão no Manifest** — é necessário solicitar **dinamicamente**, verificando se o usuário já concedeu ou não o acesso.

📌 Exemplo de verificação e solicitação de permissão (câmera):

```java
if (ContextCompat.checkSelfPermission(this, Manifest.permission.CAMERA)
        != PackageManager.PERMISSION_GRANTED) {

    ActivityCompat.requestPermissions(this,
            new String[]{Manifest.permission.CAMERA}, 1);
}
