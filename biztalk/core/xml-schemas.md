---
title: Esquemas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ec364e7-866d-4164-be91-be75a40ce878
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b46f5b43a34049dfc3ad366fd87fa82d6dac2cb7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997493"
---
# <a name="xml-schemas"></a>Esquemas XML
Un esquema XML describe un documento empresarial que se representa en lenguaje XML. Dado que Microsoft BizTalk Server usa XML como representación canónica para documentos empresariales, los documentos entrantes y salientes no necesitan ninguna traducción. Los esquemas XML se pueden crear en el Editor de BizTalk mediante el uso únicamente del conjunto básico de propiedades que está disponible en todos los esquemas y no precisan que se habilite ninguna extensión del editor de esquemas.  
  
 Hay varias maneras en que puede crear esquemas XML en BizTalk Server. Estos incluyen:  
  
- **Crear un nuevo esquema**. Este método de creación de esquemas implica agregar un esquema nuevo al proyecto de BizTalk. En **el Explorador de soluciones**, haga clic en el proyecto de BizTalk, haga clic en **agregar**, haga clic en **nuevo elemento**y, a continuación, haga clic en **esquema**. Construir la estructura del esquema agregando varios nodos en la vista de árbol de esquema.  
  
- **Crear un nuevo esquema, junto con otros esquemas**. En el caso de los habituales esquemas complejos que se presentan en la realidad, lo más probable es que cree los esquemas de los mensajes mediante el uso de tipos proporcionados en otros esquemas existentes. Si utiliza los conceptos de importar, incluir y redefinir esquemas del lenguaje de definición de esquemas XML (XSD), puede aprovechar los tipos que ya estén definidos en otros esquemas. Para obtener más información sobre el uso de varios esquemas juntas, consulte [esquemas que usan otros esquemas](../core/schemas-that-use-other-schemas.md).  
  
- **Generar un esquema desde un mensaje de instancia**. Puede generar un esquema XML que se corresponda con un mensaje de instancia concreto siempre y cuando dicho mensaje contenga código XML bien estructurado. Use la **agregar elementos generados - *\<el nombre del proyecto de BizTalk\>***  cuadro de diálogo, puede obtener acceso haciendo **agregar elementos generados** en el **Proyecto** menú para realizar este tipo de operación de generación de esquema.  
  
  > [!NOTE]
  >  Este tipo de operación de generación solo se puede usar para generar esquemas XML; no es válido para esquemas de propiedades ni esquemas de archivos sin formato.  
  
- **Migrar un esquema desde un lenguaje de especificación de esquema anterior a XSD**. Puede generar un esquema XML para BizTalk Server desde un esquema que se desarrolló con una versión anterior de BizTalk Server, que almacena los esquemas en formato de datos XML reducidos (XDR). Para obtener más información sobre cómo migrar esquemas XDR antiguos al formato XSD utilizado por BizTalk Server, consulte [esquema migración desde versiones anteriores de BizTalk Server](../core/schema-migration-from-previous-versions-of-biztalk-server.md).  
  
   También puede generar un esquema XML basado en XSD a partir de un esquema de documento concreto mediante la sintaxis DTD (definición de tipo de documento).  
  
   Use la **agregar elementos generados - *\<el nombre del proyecto de BizTalk\>***  cuadro de diálogo, puede obtener acceso haciendo **agregar elementos generados** en el **Proyecto** menú para realizar este tipo de operación de generación de esquema.  
  
  > [!NOTE]
  >  Estos tipos de operaciones de generación solo se pueden usar para generar esquemas XML; no son válidos para esquemas de propiedades ni esquemas de archivos sin formato.  
  
  Ya utilice una u otra técnica de creación de esquemas, a continuación deberá modificar el esquema para que proporcione una descripción suficientemente completa de los mensajes de instancia correspondientes. Para empezar a trabajar en estas tareas, consulte [administrar los nodos de esquema](../core/managing-the-nodes-within-a-schema.md), [establecer las propiedades de nodo](../core/how-to-set-node-properties.md), y [trabajar con nodos existentes](../core/working-with-existing-nodes.md).  
  
## <a name="see-also"></a>Vea también  
 [Tipos de esquemas de BizTalk](../core/different-types-of-biztalk-schemas.md)