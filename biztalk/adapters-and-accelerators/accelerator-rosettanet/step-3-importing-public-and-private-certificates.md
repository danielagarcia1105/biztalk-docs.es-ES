---
title: 'Paso 3: Importar Public y Private certificados | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public certificates
- importing certificates
- private certificates
- double action tutorial, importing certificates
- certificates, importing
ms.assetid: 955bdd69-9fbc-4100-ab8a-8f5dd4a17cbb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46d087c44cac350df2d58c880303668b5c3e0c24
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966954"
---
# <a name="step-3-importing-public-and-private-certificates"></a>Paso 3: Importar Public y Private certificados
En este paso, importar los certificados se crean en [paso 2: crear pública y privada certificados &#91; RN3 &#93; ](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md) a los equipos de Contoso y Fabrikam. Cada equipo importa sus propios certificados privadas e importa los certificados públicos de la otra organización.  
  
> [!NOTE]
>  Tendrá que transferir los certificados privados de Fabrikam y Contoso públicos certificados en el equipo de Fabrikam para importarlos. Este paso se asume que estos certificados se coloquen en la carpeta C:\Certs en el equipo de Fabrikam.  
  
### <a name="to-import-the-contoso-private-certificates-on-the-contoso-computer"></a>Para importar los certificados privados de Contoso en el equipo de Contoso  
  
1.  En el equipo de Contoso, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  En el símbolo del sistema, vaya a  **\<**  *unidad***\>: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK** y, a continuación, presione **ENTRAR**.  
  
3.  En el símbolo del sistema, escriba **CertWizard /Privatekey "\<***unidad***\>: \Certs\Contoso Encryption.pfx privada"** y, a continuación, presione **Escriba**.  
  
4.  En el **escriba la contraseña para el archivo de certificado** escriba **mysecret**y, a continuación, presione **ENTRAR**.  
  
5.  En el **escriba una contraseña para la identidad < contoso_machine > \HostSvc** símbolo del sistema, escriba la contraseña de la cuenta de HostSvc y, a continuación, presione **ENTRAR**.  
  
    > [!NOTE]
    >  Si su BizTalkServerApplication se ejecuta con un nombre de cuenta que no sea HostSvc, el símbolo del sistema debe ser diferente.  
  
6.  En el **este certificado principal se usará para** escriba **d.** y, a continuación, presione **ENTRAR**.  
  
     El CertWizard importa el certificado en el almacén de \Personal\Certificates para las cuentas de usuario que se ejecutan los hosts AplicaciónBizTalkServer y BizTalkServerIsolatedHost en.  
  
7.  Repita los pasos 3 a 6 para el certificado privado de Contoso Signature.pfx que especifica que es un certificado de firma escribiendo **S** en el **este certificado principal se usará para** símbolo del sistema que anotó en el paso 6.  
  
### <a name="to-import-the-fabrikam-public-certificates-on-the-contoso-computer"></a>Para importar los certificados públicos de Fabrikam en el equipo de Contoso  
  
1.  En el equipo de Contoso, haga clic en **iniciar**, haga clic en **ejecutar,** tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  En el símbolo del sistema, vaya a  *\<unidad\>***: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK** y, a continuación, Presione **ENTRAR**.  
  
3.  En el símbolo del sistema, escriba **/PublicKey CertWizard "***\<unidad\>***: \Certs\Fabrikam Encryption.cer pública"** y, a continuación, presione  **Escriba**.  
  
4.  Repita el paso 3 para el certificado público Signature.cer de Fabrikam.  
  
### <a name="to-import-the-fabrikam-private-certificates-on-the-fabrikam-computer"></a>Para importar los certificados privados de Fabrikam en el equipo de Fabrikam  
  
1.  Copie los siguientes archivos desde el equipo de Contoso a la \<unidad\>: \Certs carpeta en el equipo de Fabrikam: Encryption.cer públicas de Contoso, Signature.cer públicas de Contoso, Fabrikam privada Encryption.pfx y privados de Fabrikam Signature.pfx.  
  
2.  En el equipo Fabrikum, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En el símbolo del sistema, vaya a  *\<unidad\>***: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK** y, a continuación, Presione **ENTRAR**.  
  
4.  En el símbolo del sistema, escriba **CertWizard /Privatekey "***\<unidad\>***: \Certs\Fabrikam Encryption.pfx privada"** y, a continuación, presione **Escriba**.  
  
5.  En el **escriba la contraseña para el archivo de certificado** escriba **mysecret**y, a continuación, presione **ENTRAR**.  
  
6.  En el **escriba una contraseña para la identidad < fabrikam_machine > \HostSvc** símbolo del sistema, escriba la contraseña de la cuenta de HostSvc y, a continuación, presione **ENTRAR**.  
  
    > [!NOTE]
    >  Si su BizTalkServerApplication se ejecuta con un nombre de cuenta que no sea HostSvc, el símbolo del sistema debe ser diferente.  
  
7.  En el **este certificado principal se usará para** escriba **d.** y, a continuación, presione **ENTRAR**.  
  
     El CertWizard importa el certificado en el almacén de \Personal\Certificates para las cuentas de usuario que se ejecutan los hosts AplicaciónBizTalkServer y BizTalkServerIsolatedHost en.  
  
8.  Repita los pasos del 4 al 7 para el certificado de Fabrikam privada Signature.pfx para especificar que es un certificado de firma escribiendo **S** en el **este certificado principal se usará para** símbolo del sistema en el paso 6.  
  
### <a name="to-import-the-contoso-public-certificates-on-the-fabrikam-computer"></a>Para importar los certificados públicos de Contoso en el equipo de Fabrikam  
  
1.  En el equipo Fabrikum, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  En el símbolo del sistema, vaya a  *\<unidad\>***: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK** y, a continuación, Presione **ENTRAR**.  
  
3.  En el símbolo del sistema, escriba **/PublicKey CertWizard "***\<unidad\>***: \Certs\Contoso Encryption.cer pública"** y, a continuación, presione  **Escriba**.  
  
4.  Repita el paso 3 para el certificado público Signature.cer de Contoso.  
  
## <a name="see-also"></a>Vea también  
 [Paso 4: Habilitar Capa de sockets seguros en IIS](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)