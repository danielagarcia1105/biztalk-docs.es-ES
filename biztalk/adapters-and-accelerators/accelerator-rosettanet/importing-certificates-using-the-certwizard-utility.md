---
title: Importación de certificados mediante la utilidad CertWizard | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, root keys
- certificates, public keys
- certificates, private keys
- importing certificates
- public keys
- private keys
- CertWizard utility
- certificates, importing
- root keys
ms.assetid: 0c54d7ab-69cf-4f4a-b976-6f740a41280b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50bdce5ff094153e0aaa0e6ca69b106993722722
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993805"
---
# <a name="importing-certificates-using-the-certwizard-utility"></a>Importación de certificados mediante la utilidad CertWizard
En este tema se describe cómo importar un certificado mediante la utilidad CertWizard, una utilidad de línea de comandos de paso a paso disponible en Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK. En este tema describe la importación de una clave raíz, pública o privada. Describe los modificadores que se utilizan para configurar el certificado.  
  
 La utilidad CertWizard automatiza muchos de los pasos que debe realizar manualmente mediante el uso de Microsoft Management Console (MMC). La utilidad CertWizard realiza el **runas** comando para abrir MMC como la cuenta de servicio de host. Si no se agrega un **Useridentity** switch, se detectará y usar la cuenta de servicio de host, que le solicitará una contraseña. Almacena y se configura el certificado.  
  
 Puede importar varios certificados al mismo tiempo mediante la creación de un archivo por lotes con varios comandos de la utilidad CertWizard.  
  
### <a name="to-import-a-private-key"></a>Para importar una clave privada  
  
1. Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
2. En el símbolo del sistema, vaya a la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] carpeta del SDK con MS-DOS **CD** comando, por ejemplo, escriba **cd C:\Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK** .  
  
   > [!NOTE]
   >  ¿Para obtener ayuda con la utilidad CertWizard, escriba **CertWizard /?** en el símbolo del sistema.  
  
3. En el símbolo del sistema, escriba **CertWizard /Privatekey \<filename\>.pfx**, donde \< *filename*\>.pfx contiene el certificado privado. Para proporcionar la contraseña para el archivo, anexar **/Filepassword \<filepassword\>**  al comando.  
  
4. Si desea importar el certificado en una cuenta específica utilizada por el Host de BizTalk, en anexos **/Useridentity \<useridentity\> /Password \<contraseña\>**  al comando.  
  
5. Si desea designar una huella digital específica en caso de que el archivo .pfx contiene más de un certificado, en anexos **/Thumbprint \<huella digital\>**  al comando.  
  
6. Si desea configurar el uso del certificado, anexar **/Usage como** al comando y, a continuación, anexe uno de los valores siguientes:  
  
   -   Anexar **sesión** para agregar la huella digital del certificado como certificado de firma para el grupo de BizTalk. como está establecido en el cuadro de diálogo para Microsoft BizTalk Server (Local) en la consola de administración de BizTalk.  
  
   -   Anexar **descifrar** para agregar la huella digital del certificado como certificado de descifrado para los Hosts de BizTalk, como está establecido en la ficha certificado de las páginas de propiedades para cada host en la consola de administración de BizTalk.  
  
   -   Anexar **ambos** para agregar el certificado de huella digital para tanto el grupo BizTalk de firma de certificado y el certificado de descifrado del BizTalk Host.  
  
   -   Anexar **ninguno** cuando no desea establecer la configuración para el grupo de BizTalk o los Hosts de BizTalk.  
  
7. Si desea configurar el certificado como exportable, anexar **/Exportable true**. Para establecer el certificado como no exportable, anexar **/Exportable false**, que es el comportamiento predeterminado.  
  
8. Presione **ENTRAR**.  
  
9. Si no escribió una de las contraseñas necesarias en el comando, la herramienta le pide para él. Escriba la contraseña y, a continuación, presione **ENTRAR**.  
  
10. Si el archivo contiene varios certificados, pero no escribió una huella digital en el comando, la herramienta muestra las huellas digitales disponibles y le pide que seleccione uno. Escriba el número de la huella digital que desee y, a continuación, presione **ENTRAR**.  
  
     La herramienta importa el certificado en el almacén de \Personal\Certificates para el usuario especificado en el **/useridentity** cambie. Si no especifica un usuario, el usuario predeterminado es la identidad del usuario para el host de BizTalkServerApplication y BizTalkServerIsolatedHost.  
  
### <a name="to-import-a-public-key"></a>Para importar una clave pública  
  
1. Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
2. En el símbolo del sistema, vaya a la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] carpeta del SDK mediante el uso de MS-DOS **CD** comando, por ejemplo, escriba **cd C:\Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK**.  
  
3. En el símbolo del sistema, escriba **/PublicKey CertWizard \<filename\>.cer**, donde \< *filename*\>.cer contiene el certificado público.  
  
4. Si desea designar una huella digital del certificado en el archivo .cer o .der, anexar **/Thumbprint \<huella digital\>**  al comando.  
  
    La herramienta importa el certificado en el almacén de certificados (equipo Local) \Other People\Certificates y establece su configuración.  
  
### <a name="to-import-a-root-key"></a>Para importar una clave de raíz  
  
1. Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
2. En el símbolo del sistema, vaya a la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] carpeta del SDK mediante el uso de MS-DOS **CD** comando, por ejemplo, escriba **cd C:\Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK**.  
  
3. En el símbolo del sistema, escriba **CertWizard /Rootkey \<filename\>.cer**, donde \< *filename*\>.cer contiene el certificado raíz.  
  
4. Si desea designar una huella digital del certificado en el archivo .cer o .der, anexar **/Thumbprint \<huella digital\>**  al comando.  
  
    La herramienta importa el certificado en el almacén de certificados (equipo Local) \Trusted Root Certification Authority\Certificates y establece su configuración.  
  
## <a name="see-also"></a>Vea también  
 [CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)   
 [Administración de certificados](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)