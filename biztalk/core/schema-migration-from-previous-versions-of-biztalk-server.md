---
title: "Migración de esquema desde versiones anteriores de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bdc86401-2002-40b8-a919-2c00cf42b557
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1666e7cc8459fd4418e0ba0963caf5b654975805
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="schema-migration-from-previous-versions-of-biztalk-server"></a>Migración de esquemas de versiones anteriores de BizTalk Server
Esta versión de BizTalk Server usa el lenguaje de definición de esquemas XML (XSD) para representar los esquemas de mensajes, mientras que las versiones anteriores utilizaban la sintaxis de datos reducidos XML (XDR) para representarlos. Si migra desde una versión anterior de BizTalk Server, debe convertir los esquemas para que utilicen XSD en lugar de XDR.  
  
 Debe realizar las siguientes tareas para convertir un esquema de BizTalk de la sintaxis XDR a la sintaxis XSD:  
  
-   Cambie la extensión del archivo de esquema de .xdr a .xsd.  
  
-   Agregue el esquema cuyo nombre ha cambiado al proyecto de BizTalk correspondiente.  
  
-   Convierta el esquema cuyo nombre ha cambiado de XDR a XSD. Para ello, abra el esquema en el Editor de BizTalk.  
  
-   Guarde el esquema para que la conversión se almacene de forma permanente.  
  
 Para obtener información detallada sobre cómo realizar estos pasos, consulte [cómo migrar esquemas XDR en esquemas XSD](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md).  
  
## <a name="see-also"></a>Vea también  
 [Acerca de los esquemas](../core/about-schemas.md)   
 [Cómo migrar esquemas XDR en esquemas XSD](../core/how-to-migrate-xdr-schemas-to-xsd-schemas.md)   
 [Migrar registros de archivo sin formato](../core/migrating-flat-file-records.md)