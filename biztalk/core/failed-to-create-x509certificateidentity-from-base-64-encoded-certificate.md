---
title: No se pudo crear X509CertificateIdentity a partir de certificado codificado en base 64 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a13112bd-e0e8-4b49-ad2f-ea82b2e8162f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31cf07660b939beb3ea1a79fd0f34390f873d5cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="failed-to-create-x509certificateidentity-from-base-64-encoded-certificate"></a>No se pudo crear X509CertificateIdentity a partir de un certificado codificado base 64.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No se pudo crear X509CertificateIdentity a partir de un certificado codificado base 64.|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que el adaptador no pudo crear la identifidad de extremo X509Certificate debido a una opción de configuración de certificado no válida.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para configurar certificados.  
  
#### <a name="to-configure-certificates"></a>Para configurar certificados  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  
  
2.  En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3.  Busque la aplicación y, a continuación, busque su transporte.  
  
4.  Haga clic con el botón secundario en el nombre del transporte.  
  
5.  Haga clic en **Propiedades**.  
  
6.  En el puerto **tipo** , seleccione el puerto correcto.  
  
7.  Haga clic en **configurar**.  
  
8.  En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **seguridad** ficha.  
  
9. Asegúrese de que la configuración es correcta para el **huella digital del certificado de cliente** y **huella digital del certificado de servicio**.