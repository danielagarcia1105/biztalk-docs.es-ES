---
title: "Importación de certificados mediante MMC | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, public keys
- certificates, private keys
- importing certificates
- public keys
- private keys
- certificates, importing
ms.assetid: 58fb1711-e295-4aa6-902e-e28e4a2cd921
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 466917e0656dfa39467a00dfa91285b3cb7cf1a1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="importing-certificates-using-mmc"></a>Importación de certificados mediante MMC
Este tema describe cómo importar un digital de certificado que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] utiliza para autenticar a un socio comercial, descifrar un mensaje entrante, o cifrar o firmar un mensaje saliente.  
  
 Este procedimiento utiliza el complemento de certificados para el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console (MMC). Este proceso manual importa un certificado en el almacén de certificados, que sea necesario configurar el uso de certificados por separado. También puede importar un certificado mediante la utilidad CertWizard que configura automáticamente el uso de los certificados automáticamente.  
  
 Para importar certificados privada, debe usar las cuentas de usuario en la que se ejecutan los Hosts de BizTalk.  
  
### <a name="to-import-a-public-key-certificate"></a>Para importar un certificado de clave pública  
  
1.  Copia el certificado de clave pública (.cer) del archivo a una ubicación en el disco duro del servidor al que va a copiar certificados.  
  
2.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración de**.  
  
3.  En el [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expanda **certificados (equipo Local)**. El usuario ha iniciado la sesión debe tener permisos administrativos en el equipo.  
  
4.  Haga clic en **otras personas**, seleccione **todas las tareas**y, a continuación, haga clic en **importación**.  
  
5.  En el **principal del Asistente para certificados importación** página, haga clic en **siguiente**.  
  
6.  En el **archivo para importar** página, haga clic en **examinar** y busque la carpeta que contiene los archivos de certificado. Seleccione el archivo desde el que desea importar el certificado y, a continuación, haga clic en **abiertos**.  
  
7.  En el **almacén de certificados** página, seleccione **seleccionar automáticamente el certificado según el tipo de certificado** o **colocar todos los certificados en el siguiente almacén**. Si selecciona **colocar todos los certificados en el siguiente almacén**, haga clic en **examinar**, seleccione el almacén de certificados, haga clic en **Aceptar**y, a continuación, haga clic en **siguiente**.  
  
8.  Haga clic en **Finalizar**.  
  
### <a name="to-import-a-private-key-certificate"></a>Para importar un certificado de clave privada  
  
1.  Certificado de clave privada (.pfx) copia archivos en una ubicación en el disco duro del servidor al que va a copiar certificados.  
  
2.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **ejecutar como/User:\<hospedar servicio\> mmc**y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Para \< *hospedar servicio*\>, escriba el nombre del servicio que se selecciona automáticamente para el servicio de host cuando instaló [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].  
  
3.  Escriba la contraseña de \< *hospedar servicio*\>y, a continuación, presione **ENTRAR**.  
  
4.  En [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] consola de administración, en la **archivo** menú, haga clic en **agregar o quitar complemento**.  
  
5.  En el cuadro de diálogo Agregar o quitar complemento, haga clic en **agregar**.  
  
6.  En el cuadro de diálogo Add Standalone Snap-in, seleccione **certificados**, haga clic en **agregar**, haga clic en **cerrar**y, a continuación, haga clic en **Aceptar**.  
  
7.  En [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Management Console, expanda **certificados - usuario actual**, haga clic en **Personal**, seleccione **todas las tareas**y, a continuación, haga clic en  **Importación**.  
  
8.  En el **principal del Asistente para certificados importación** página, haga clic en **siguiente**.  
  
9. En el **archivo para importar** página, haga clic en **examinar** y busque la carpeta que contiene el archivo de certificado .pfx que contiene el certificado que desea importar. Seleccione el archivo adecuado y, a continuación, haga clic en **abiertos**.  
  
10. En el **contraseña** página, en la **contraseña** , escriba la contraseña para el archivo de clave privada.  
  
11. Seleccione **Habilitar protección segura de clave privada** o **marcar esta clave como exportable**y, a continuación, haga clic en **siguiente**.  
  
12. En el **almacén de certificados** página, seleccione **seleccionar automáticamente el certificado según el tipo de certificado** o **colocar todos los certificados en el siguiente almacén**. Si selecciona **colocar todos los certificados en el siguiente almacén**, haga clic en **examinar**, seleccione el almacén, haga clic en **Aceptar**y, a continuación, haga clic en **siguiente**.  
  
13. En el **completar el Asistente para importación de certificados** página, haga clic en **finalizar**.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de certificados importados con MMC](../../adapters-and-accelerators/accelerator-rosettanet/configuring-certificates-imported-using-mmc.md)   
 [CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)