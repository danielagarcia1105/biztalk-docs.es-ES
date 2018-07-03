---
title: 'Paso 3: Importar certificados públicos y privados | Microsoft Docs'
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
ms.openlocfilehash: 18074fd3b72322d79e10895214352837ccf907bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002349"
---
# <a name="step-3-importing-public-and-private-certificates"></a>Paso 3: Importar certificados públicos y privados
En este paso, importar los certificados que creó en [paso 2: crear públicas y privadas certificados &#91;RN3&#93; ](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md) a los equipos de Contoso y Fabrikam. Cada equipo importa sus propios certificados privados y los importa los certificados públicos de la otra organización.  
  
> [!NOTE]
>  Tendrá que transferir los certificados privados de Fabrikam y los certificados públicos de Contoso para el equipo de Fabrikam para importarlos. Este paso se da por supuesto que coloca estos certificados en la carpeta C:\Certs en el equipo de Fabrikam.  
  
### <a name="to-import-the-contoso-private-certificates-on-the-contoso-computer"></a>Para importar los certificados privados de Contoso en el equipo de Contoso  
  
1. En el equipo de Contoso, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2. En el símbolo del sistema, vaya a **\<** <em>unidad</em>**\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK** y, a continuación, presione **ENTRAR**.  
  
3. En el símbolo del sistema, escriba **CertWizard /Privatekey "\<**<em>unidad</em>**\>: \Certs\Contoso Private Encryption.pfx"** y, a continuación, presione **Escriba**.  
  
4. En el **escriba la contraseña del archivo de certificado** escriba **MiSecreto**y, a continuación, presione **ENTRAR**.  
  
5. En el **escriba la contraseña para la identidad < contoso_machine > \HostSvc** símbolo del sistema, escriba la contraseña de cuenta HostSvc y, a continuación, presione **ENTRAR**.  
  
   > [!NOTE]
   >  Si su BizTalkServerApplication se ejecuta con un nombre de cuenta que no sea HostSvc, el símbolo del sistema debe ser diferente.  
  
6. En el **se usará este certificado principal para** escriba **d.** y, a continuación, presione **ENTRAR**.  
  
    El CertWizard importa el certificado en el almacén de \Personal\Certificates para las cuentas de usuario que ejecutará hosts BizTalkServerApplication y BizTalkServerIsolatedHost.  
  
7. Repita los pasos del 3 al 6 para el certificado privado de Contoso Signature.pfx especificar que es un certificado de firma escribiendo **S** en el **se usará este certificado principal para** símbolo del sistema que anotó en el paso 6.  
  
### <a name="to-import-the-fabrikam-public-certificates-on-the-contoso-computer"></a>Para importar los certificados públicos de Fabrikam en el equipo de Contoso  
  
1.  En el equipo de Contoso, haga clic en **iniciar**, haga clic en **ejecutar,** tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  En el símbolo del sistema, vaya a  *\<unidad\>** *:\Program comunes\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK** y, a continuación, presione **ENTRAR** .  
  
3.  En el símbolo del sistema, escriba **/PublicKey CertWizard "***\<unidad\>***: \Certs\Fabrikam Encryption.cer pública"** y, a continuación, presione **ENTRAR** .  
  
4.  Repita el paso 3 para el certificado público Signature.cer de Fabrikam.  
  
### <a name="to-import-the-fabrikam-private-certificates-on-the-fabrikam-computer"></a>Para importar los certificados privados de Fabrikam en el equipo de Fabrikam  
  
1.  Copie los siguientes archivos desde el equipo de Contoso a la \<unidad\>: \Certs carpeta en el equipo de Fabrikam: Encryption.cer público de Contoso, Signature.cer público de Contoso, Fabrikam privada Encryption.pfx y privados de Fabrikam Signature.pfx.  
  
2.  En el equipo Fabrikum, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En el símbolo del sistema, vaya a  *\<unidad\>** *:\Program comunes\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK** y, a continuación, presione **ENTRAR** .  
  
4.  En el símbolo del sistema, escriba **CertWizard /Privatekey "***\<unidad\>***: \Certs\Fabrikam Private Encryption.pfx"** y, a continuación, presione **ENTRAR**.  
  
5.  En el **escriba la contraseña del archivo de certificado** escriba **MiSecreto**y, a continuación, presione **ENTRAR**.  
  
6.  En el **escriba la contraseña para la identidad < fabrikam_machine > \HostSvc** símbolo del sistema, escriba la contraseña de cuenta HostSvc y, a continuación, presione **ENTRAR**.  
  
    > [!NOTE]
    >  Si su BizTalkServerApplication se ejecuta con un nombre de cuenta que no sea HostSvc, el símbolo del sistema debe ser diferente.  
  
7.  En el **se usará este certificado principal para** escriba **d.** y, a continuación, presione **ENTRAR**.  
  
     El CertWizard importa el certificado en el almacén de \Personal\Certificates para las cuentas de usuario que ejecutará hosts BizTalkServerApplication y BizTalkServerIsolatedHost.  
  
8.  Repita los pasos del 4 al 7 para el certificado de Fabrikam privada Signature.pfx especifica que es un certificado de firma escribiendo **S** en el **se usará este certificado principal para** símbolo del sistema en el paso 6.  
  
### <a name="to-import-the-contoso-public-certificates-on-the-fabrikam-computer"></a>Para importar los certificados públicos de Contoso en el equipo de Fabrikam  
  
1.  En el equipo Fabrikum, haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2.  En el símbolo del sistema, vaya a  *\<unidad\>** *:\Program comunes\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK** y, a continuación, presione **ENTRAR** .  
  
3.  En el símbolo del sistema, escriba **/PublicKey CertWizard "***\<unidad\>***: \Certs\Contoso Encryption.cer pública"** y, a continuación, presione **ENTRAR**.  
  
4.  Repita el paso 3 para el certificado Signature.cer público de Contoso.  
  
## <a name="see-also"></a>Vea también  
 [Paso 4: Habilitar Capa de sockets seguros en IIS](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)