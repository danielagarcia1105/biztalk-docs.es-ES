---
title: "Creación y uso de esquemas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generating schemas
- schemas
- creating schemas
- schemas, generating
ms.assetid: 3927b0b3-db3b-4494-b003-d930af734e58
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f10275c5ed0b887907c7b26b7d1ce8ad5003b099
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-using-schemas"></a>Creación y uso de esquemas
El Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service (EMS) usa esquemas que se crean con un editor XML o con el Editor de BizTalk Server en Visual Studio (solo si usa el adaptador en una orquestación). El esquema describe el tipo de información que espera. Este tema contiene información para un controlador tanto de envío como de recepción.  
  
 Los esquemas que cree para su uso con el Adaptador de BizTalk para TIBCO Enterprise Message Service deben tener un espacio de nombres de destino. BizTalk Server requiere el espacio de nombres de destino debido a que es la clave que asocia una instancia de mensaje dada con una orquestación dada. Es decir, una orquestación se suscribe a cualquier mensaje que tenga un espacio de nombres de destino específico y se proporciona un mensaje XML entrante que tenga dicho espacio de nombres de destino a cada orquestación suscrita al mensaje. Si un esquema de documento XML no tiene un espacio de nombres de destino, BizTalk Server usa el nombre del elemento raíz como clave.  
  
## <a name="generating-a-schema"></a>Generar un esquema  
 En los siguientes procedimientos se muestra cómo generar un esquema y cómo establecer el espacio de nombres de destino.  
  
#### <a name="to-generate-a-schema-using-biztalk-editor"></a>Para generar un esquema mediante el Editor de BizTalk  
  
1.  En el Editor de BizTalk, abra el proyecto.  
  
2.  En el Explorador de soluciones en la superior derecha, seleccione **agregar**y, a continuación, seleccione **agregar elementos generados**.  
  
3.  En el **plantillas** panel, seleccione **generar esquemas**y, a continuación, haga clic en **agregar**.  
  
4.  En el **generar esquemas** cuadro de diálogo, en la **tipo de documento** lista, seleccione **XML bien formado**.  
  
5.  Haga clic en **examinar** para buscar el archivo de entrada para el que desea generar un esquema y, a continuación, haga clic en **Aceptar**.  
  
     A continuación, debe establecer el espacio de nombres de destino.  
  
#### <a name="to-set-the-target-namespace"></a>Para establecer el espacio de nombres de destino  
  
1.  En el Editor de BizTalk, abra el archivo de esquema, haga clic en  **\<esquema >**y, a continuación, seleccione **propiedades**.  
  
2.  En el **propiedades** panel, busque el **Namespace** campo y escriba un nombre, por ejemplo, `testNameSpace`.  
  
 A continuación, puede continuar con la orquestación mediante mensajes. Cuando se selecciona un mensaje, BizTalk Server encuentra una orquestación que usa un esquema con un espacio de nombres de destino establecido y se sigue el proceso de orquestación.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de aplicaciones](../core/developing-applications5.md)