---
title: "Cómo usar la utilidad de seguimiento de Host para SSO iniciado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host initiated SSO, trace utility
- trace utility
ms.assetid: a53444d1-3f63-42a6-8ee6-b60ff9af9e41
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebb2003cc6091e3f14bd863902e03649d9005722
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-the-trace-utility-in-host-initiated-sso"></a>Cómo usar la utilidad de seguimiento de Host para SSO iniciado
El seguimiento constituye el método principal para solucionar problemas.  
  
## <a name="tracing"></a>Seguimiento  
 Utilice la línea de comandos de seguimiento para habilitar el seguimiento en SSO.  
  
> [!NOTE]
>  Para que este comando funcione, el archivo tracelog.exe debe encontrarse en el siguiente directorio:  
>   
>  \<*unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On  
  
> [!NOTE]
>  Puede descargar este archivo en la siguiente ubicación: [http://go.microsoft.com/fwlink/?LinkId=59534](http://go.microsoft.com/fwlink/?LinkId=59534)  
  
#### <a name="to-use-the-trace-utility"></a>Para utilizar la utilidad de seguimiento  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de **Trace – start – high** para establecer el nivel de seguimiento como alto y comenzar el seguimiento.  
  
5.  Ejecute el escenario con el SSO iniciado por host.  
  
6.  Tipo de **Trace – stop** para finalizar el seguimiento. En el directorio anterior se generará un archivo .bin que podrá enviar a Microsoft para su análisis.  
  
## <a name="see-also"></a>Vea también  
 [SSO iniciado por host](../core/host-initiated-sso.md)