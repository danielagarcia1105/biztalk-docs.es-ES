---
title: Crear y utilizar esquemas en TIBCO | Documentos de Microsoft
description: Utilice el Editor de BizTalk para crear un esquema para el adaptador de BizTalk para TIBCO Enterprise Message Service y establecer el espacio de nombres de destino en el esquema de BizTalk Server
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3927b0b3-db3b-4494-b003-d930af734e58
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 384d140832c123f46ecf531e64b3c1ca11e64f4e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968722"
---
# <a name="create-and-use-tibco-schemas"></a>Crear y utilizar esquemas TIBCO

## <a name="overview"></a>Información general
El Adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service (EMS) usa esquemas que se crean con un editor XML o con el Editor de BizTalk Server en Visual Studio (solo si usa el adaptador en una orquestación). El esquema describe el tipo de información que espera. Este tema contiene información para un controlador tanto de envío como de recepción.  
  
Los esquemas que cree para su uso con el Adaptador de BizTalk para TIBCO Enterprise Message Service deben tener un espacio de nombres de destino. BizTalk Server requiere el espacio de nombres de destino debido a que es la clave que asocia una instancia de mensaje dada con una orquestación dada. Es decir, una orquestación se suscribe a cualquier mensaje que tenga un espacio de nombres de destino específico y se proporciona un mensaje XML entrante que tenga dicho espacio de nombres de destino a cada orquestación suscrita al mensaje. Si un esquema de documento XML no tiene un espacio de nombres de destino, BizTalk Server usa el nombre del elemento raíz como clave.  

Los pasos siguientes muestran cómo generar un esquema y cómo establecer el espacio de nombres de destino.  
  
## <a name="generate-a-schema"></a>Generar un esquema    
 
1.  En el Editor de BizTalk, abra el proyecto.  
  
2.  En el Explorador de soluciones en la superior derecha, seleccione **agregar**y, a continuación, seleccione **agregar elementos generados**.  
  
3.  En el **plantillas** panel, seleccione **generar esquemas**y, a continuación, haga clic en **agregar**.  
  
4.  En el **generar esquemas** cuadro de diálogo, en la **tipo de documento** lista, seleccione **XML bien formado**.  
  
5.  Haga clic en **examinar** para buscar el archivo de entrada para el que desea generar un esquema y, a continuación, haga clic en **Aceptar**.  
  
A continuación, establezca el espacio de nombres de destino.  
  
## <a name="set-the-target-namespace"></a>Establecer el espacio de nombres de destino  
  
1.  En el Editor de BizTalk, abra el archivo de esquema, haga clic en  **\<esquema\>** y, a continuación, seleccione **propiedades**.  
  
2.  En el **propiedades** panel, busque el **Namespace** campo y escriba un nombre, por ejemplo, `testNameSpace`.  
  
 A continuación, puede continuar con la orquestación mediante mensajes. Cuando se selecciona un mensaje, BizTalk Server encuentra una orquestación que usa un esquema con un espacio de nombres de destino establecido y se sigue el proceso de orquestación.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de aplicaciones](../core/developing-applications5.md)