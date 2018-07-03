---
title: Exportación de certificados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exporting certificates
- certificates, exporting
ms.assetid: edeeb300-19d6-44a8-b730-dcd15891cdf9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f5a4390cc62fdb46cbad9993a106d98163c0838
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975869"
---
# <a name="exporting-certificates"></a>Exportación de certificados
En este tema se describe cómo exportar un certificado mediante el Asistente para exportación de certificados. Use este asistente para exportar un certificado público o un certificado privado.  
  
### <a name="to-export-a-partner-certificate"></a>Para exportar un certificado de un socio comercial  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.  
  
2. Expanda **Certificados (equipo local)** y **Otras personas**, y haga clic en **Certificados**.  
  
3. En el panel derecho, haga clic con el botón secundario en el nombre del certificado, seleccione **Todas las tareas**y, a continuación, haga clic en **Exportar**.  
  
4. En la página **Este es el Asistente para exportar certificados** , haga clic en **Siguiente**.  
  
5. En la página **Formato de archivo de exportación** , seleccione el formato que desea usar para el archivo. Generalmente, este formato es DER binario codificado x.509 para exportar un archivo codificado en binario o codificado en base 64 x.509 para exportar un archivo codificado en base 64.  
  
   > [!NOTE]
   >  La codificación de un certificado en base 64 le permite usar el certificado en un servidor UNIX.  
  
6. En la página **Archivo que se va a exportar** , haga clic en **Examinar**, indique la ubicación donde desea almacenar el archivo, escriba el nombre del archivo, haga clic en **Siguiente**y, a continuación, en **Finalizar**.  
  
### <a name="to-export-the-home-organization-certificate"></a>Para exportar el certificado de la organización principal  
  
1. Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **runas/user:\<hospedar servicio\> mmc**, donde \< *hostservice*  \> es el nombre del servicio que ha asociado con el servicio de host cuando instaló Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]y, a continuación, haga clic en **Aceptar** para ejecutar Microsoft Management Console (MMC) en el contexto del servicio de host.  
  
   > [!NOTE]
   >  Ejecute el comando **runas** para asumir la identidad del servicio de host, que se requiere para acceder al certificado de la organización principal.  
  
2. Expanda **Certificados: usuario actual**, después **Personal**y, a continuación, haga clic en **Certificados**.  
  
3. En el panel derecho, haga clic con el botón secundario en el nombre del certificado, seleccione **Todas las tareas**y, a continuación, haga clic en **Exportar**.  
  
4. En la página **Este es el Asistente para exportar certificados** , haga clic en **Siguiente**.  
  
5. Para exportar la clave pública asociada con la clave privada de un certificado, deje seleccionado **No, no exportar la clave privada** . Para exportar la clave privada, seleccione **Exportar la clave privada**.  
  
   > [!NOTE]
   >  Si selecciona **Exportar la clave privada**, se recomienda encarecidamente no enviar el archivo resultante a ningún socio comercial.  
  
   > [!NOTE]
   >  La opción **Exportar la clave privada** no estará disponible si no hizo que la clave privada fuera exportable cuando la importó por primera vez.  
  
6. En la página **Formato de archivo de exportación** , seleccione el formato que desea usar para el archivo. Generalmente, este formato es DER binario codificado x.509 para exportar un archivo codificado en binario o codificado en base 64 x.509 para exportar un archivo codificado en base 64.  
  
   > [!NOTE]
   >  La codificación de un certificado en base 64 le permite usar el certificado en un servidor UNIX.  
  
7. En la página **Archivo que se va a exportar** , haga clic en **Examinar**, indique la ubicación donde desea almacenar el archivo, escriba el nombre del archivo, haga clic en **Siguiente**y, a continuación, en **Finalizar**.  
  
## <a name="see-also"></a>Vea también  
 [Administración de certificados](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)