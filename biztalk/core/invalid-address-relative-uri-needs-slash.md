---
title: "Dirección no válida (uri relativo necesita una barra diagonal (&quot;-&quot;)) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1376f924-f119-4ba8-9be1-eea7ba5f3eb6
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa1c43d4a86af788c67ea59c7bf0ca7dea43da39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-address-relative-uri-needs-slash-quot-quot"></a>Dirección no válida (uri relativo necesita una barra diagonal (&quot;-&quot;))
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Dirección no válida; esperando un uri relativo que comience con una barra diagonal ("/").|  
  
## <a name="explanation"></a>Explicación  
 No proporcionó una ubicación de recepción WCF aislada con una dirección relativa bien formada. Por ejemplo, http://localhost/svc no funcionará como dirección relativa. No puede establecer la propiedad Dirección de la ubicación de recepción WCF aislada en una dirección absoluta.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para configurar una dirección.  
  
#### <a name="to-configure-an-address"></a>Para configurar una dirección  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** y haga clic en **administración de BizTalk Server**.  
  
2.  En la raíz de consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**.  
  
3.  Busque la aplicación y el transporte.  
  
4.  Haga clic con el botón secundario en el nombre del transporte.  
  
5.  Haga clic en **Propiedades**.  
  
6.  En el puerto **tipo** , seleccione el puerto correcto.  
  
7.  Haga clic en **configurar**.  
  
8.  En el **WCF [***tipo de transporte***] propiedades de transporte** cuadro de diálogo, haga clic en el **General** ficha.  
  
9. En el **dirección (URI)** texto, cambie la dirección. Un ejemplo de dirección relativa bien formada es /path/service.svc.  
  
 Para obtener más información sobre las ubicaciones de recepción, vea lo siguiente:  
  
-   [Cómo configurar un WCF-CustomIsolated ubicación de recepción](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [Cómo configurar un WCF-WSHttp ubicación de recepción](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [Cómo configurar un WCF-BasicHttp ubicación de recepción](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)