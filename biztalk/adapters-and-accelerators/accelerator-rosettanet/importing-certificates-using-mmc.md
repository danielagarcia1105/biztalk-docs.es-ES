---
title: Importación de certificados mediante MMC | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, public keys
- certificates, private keys
- importing certificates
- public keys
- private keys
- certificates, importing
ms.assetid: 58fb1711-e295-4aa6-902e-e28e4a2cd921
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2442551819d338d0cd78f7f7d112ffb8800aee6f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970813"
---
# <a name="importing-certificates-using-mmc"></a>Importación de certificados mediante MMC
En este tema se describe cómo importar un certificado digital que Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] usa para autenticar a un socio comercial, descifrar un mensaje entrante, o para cifrar o firmar un mensaje saliente.  
  
 Este procedimiento utiliza el complemento de certificados de Microsoft Management Console (MMC). Este proceso manual importa un certificado en el almacén de certificados, necesidad de configurar el uso de certificados por separado. También puede importar un certificado mediante la utilidad CertWizard que configura automáticamente el uso de certificado para usted.  
  
 Para importar certificados privados, debe usar las cuentas de usuario en la que se ejecutan los Hosts de BizTalk.  
  
### <a name="to-import-a-public-key-certificate"></a>Para importar un certificado de clave pública  
  
1. Copia el certificado de clave pública (.cer) del archivo a una ubicación en el disco duro del servidor al que va a copiar los certificados.  
  
2. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.  
  
3. En el [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expanda **certificados (equipo Local)**. El usuario ha iniciado sesión debe tener permisos administrativos en el equipo.  
  
4. Haga clic en **otras personas**, apunte a **todas las tareas**y, a continuación, haga clic en **importación**.  
  
5. En el **principal del Asistente para certificados importación** página, haga clic en **siguiente**.  
  
6. En el **archivo para importar** página, haga clic en **examinar** y busque la carpeta que contiene los archivos de certificado. Seleccione el archivo desde el que desea importar el certificado y, a continuación, haga clic en **abierto**.  
  
7. En el **almacén de certificados** página, seleccione **seleccionar automáticamente el certificado en función del tipo de certificado** o **colocar todos los certificados en el siguiente almacén**. Si selecciona **colocar todos los certificados en el siguiente almacén**, haga clic en **examinar**, seleccione el almacén de certificados, haga clic en **Aceptar**y, a continuación, haga clic en **siguiente**.  
  
8. Haga clic en **Finalizar**.  
  
### <a name="to-import-a-private-key-certificate"></a>Para importar un certificado de clave privada  
  
1. Certificado de clave privada (.pfx) copia archivos en una ubicación en el disco duro del servidor al que va a copiar los certificados.  
  
2. Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **de identificación de/User:\<hospedar servicio\> mmc**y, a continuación, haga clic en **Aceptar**.  
  
   > [!NOTE]
   >  Para \< *hospedar servicio*\>, escriba el nombre del servicio que se ha seleccionado automáticamente para el servicio de host cuando instaló [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].  
  
3. Escriba la contraseña de \< *hospedar servicio*\>y, a continuación, presione **ENTRAR**.  
  
4. En Microsoft Management Console, en el **archivo** menú, haga clic en **agregar o quitar complemento**.  
  
5. En el cuadro de diálogo Agregar o quitar complemento, haga clic en **agregar**.  
  
6. En el cuadro de diálogo Add Standalone Snap-in, seleccione **certificados**, haga clic en **agregar**, haga clic en **cerrar**y, a continuación, haga clic en **Aceptar**.  
  
7. En Microsoft Management Console, expanda **certificados - usuario actual**, haga clic en **Personal**, apunte a **todas las tareas**y, a continuación, haga clic en **importación**.  
  
8. En el **principal del Asistente para certificados importación** página, haga clic en **siguiente**.  
  
9. En el **archivo para importar** página, haga clic en **examinar** y busque la carpeta que contiene el archivo de certificado .pfx que contiene el certificado que desea importar. Seleccione el archivo adecuado y, a continuación, haga clic en **abierto**.  
  
10. En el **contraseña** página, en el **contraseña** , escriba la contraseña para el archivo de clave privada.  
  
11. Seleccione **Habilitar protección segura de clave privada** o **marcar esta clave como exportable**y, a continuación, haga clic en **siguiente**.  
  
12. En el **almacén de certificados** página, seleccione **seleccionar automáticamente el certificado en función del tipo de certificado** o **colocar todos los certificados en el siguiente almacén**. Si selecciona **colocar todos los certificados en el siguiente almacén**, haga clic en **examinar**, seleccione el almacén, haga clic en **Aceptar**y, a continuación, haga clic en **siguiente**.  
  
13. En el **completar el Asistente para importación de certificados** página, haga clic en **finalizar**.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de certificados importados con MMC](../../adapters-and-accelerators/accelerator-rosettanet/configuring-certificates-imported-using-mmc.md)   
 [CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)