---
title: Cómo cambiar el URI de un servicio Web consumido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, modifying
- Web services, consuming
- consuming [Web services]
- modifying, Web services
ms.assetid: 907de565-8c99-4d34-939f-fd3dba37dd11
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b9ae7d7178fc24c5f16b28325fb627045e5273a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247404"
---
# <a name="how-to-change-the-uri-of-a-consumed-web-service"></a>Cómo cambiar el URI de un servicio web consumido
Después de implementar la orquestación, BizTalk Server configura un puerto de envío para cada servicio Web al que la orquestación hace referencia. De forma predeterminada, BizTalk utiliza la URL del servicio Web en tiempo de ejecución para la misma URL para el servicio Web importado. Puede cambiar esta dirección URL mediante la consola de administración de BizTalk Server.  
  
> [!NOTE]
>  Debe implementar la orquestación antes de cambiar el URI de un servicio Web consumido. Para obtener más información sobre la implementación de la orquestación, consulte [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).  
  
### <a name="to-change-the-uri-of-a-consumed-web-service-using-biztalk-server-administration-console"></a>Para cambiar el URI de un servicio Web consumido mediante la consola de administración de BizTalk Server  
  
1.  En la consola de administración de BizTalk Server, expanda una aplicación de BizTalk y, a continuación, expanda el **puertos de envío** nodo.  
  
2.  Haga clic en un puerto de envío configurado con el adaptador de SOAP, haga clic en **propiedades**.  
  
3.  Si no tiene puertos físicos, puede crear puertos de envío y ubicaciones de recepción mediante la consola de administración de BizTalk. Para obtener información, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md).  
  
4.  En el **enviar propiedades** cuadro de diálogo, haga clic en **configurar**.  
  
5.  En el **propiedades de transporte SOAP** cuadro de diálogo, en la **dirección URL del servicio Web** , escriba la dirección URL completa para la ubicación del servicio Web y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Deberá asegurarse de que existe un servicio Web para la URL que especifique. BizTalk Server no valida la ubicación de la URL.  
  
6.  Haga clic en Aceptar para salir del **propiedades de envío** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Uso de la consola de administración de BizTalk Server](../core/using-the-biztalk-server-administration-console.md)   
 [Cómo configurar un puerto de envío de SOAP](../core/how-to-configure-a-soap-send-port.md)   
 [Encabezados SOAP con servicios Web consumidos](../core/soap-headers-with-consumed-web-services.md)   
 [Creación de puertos Web](../core/creating-web-ports.md)