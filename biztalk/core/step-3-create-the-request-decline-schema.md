---
title: 'Paso 3: Crear el esquema de declinación de solicitud | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1ce166c-1be1-4ef4-9d00-3da7038d4ada
caps.latest.revision: 39
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ff343c58e836bc0738f0200016308eb7a4d90b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278556"
---
# <a name="step-3-create-the-request-decline-schema"></a>Paso 3: Crear el esquema de declinación de la solicitud
![Paso 3 de 5](../core/media/step-3of5.gif "Step_3of5")  
  
 **Tiempo en completarse:** 7 minutos  
  
 **Objetivo:** en este paso, se creará el esquema para el mensaje [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] devuelve al almacén si el proceso empresarial rechaza la solicitud de reposición de inventario.  
  
 **Propósito:** el esquema define los datos y la estructura del mensaje de rechazo de solicitud. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]utiliza el esquema para identificar e interactuar con los datos en el mensaje.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Tenga en cuenta los siguientes requisitos antes de iniciar este paso:  
  
-   Antes de comenzar este paso debe completar [paso 1: crear el proyecto de EAISchemas](../core/step-1-create-eaischemas-project.md).  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-create-the-request-decline-schema"></a>Para crear el esquema de declinación de la solicitud  
  
1.  En el Explorador de soluciones, haga clic en el **EAISchemas** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento - EAISchemas** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Plantillas instaladas**|Haga clic en **archivos de esquema**y, a continuación, haga clic en **esquema**.|  
    |**Nombre**|Type `RequestDecline.xsd`.|  
  
3.  Haga clic en **Agregar**.  
  
4.  En el Editor de BizTalk, en el árbol de esquema, haga clic en el **raíz** nodo para seleccionarlo.  
  
5.  En el panel Propiedades, cambie el valor de la **nombre de nodo** propiedad `DeclineReq`, y, a continuación, presione ENTRAR.  
  
6.  En el árbol de esquema, haga clic en el **DeclineReq** nodo, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **elemento de campo secundario**.  
  
7.  Tipo `ReqID` como el nuevo nombre para el elemento y, a continuación, presione ENTRAR.  
  
8.  Agregar un elemento de campo secundario denominado `GrandTotal`.  
  
9. En el menú **Archivo** , haga clic en **Guardar todo**.  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha creado el esquema del mensaje que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] devuelve al almacén si el proceso empresarial rechaza la solicitud de inventario.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Creará la asignación que la orquestación necesita para crear el mensaje de declinación de la solicitud cambiando el formato del mensaje de solicitud.  
  
## <a name="see-also"></a>Vea también  
 [Paso 1: Crear el proyecto EAISchemas](../core/step-1-create-eaischemas-project.md)  
 [Paso 2: Crear el esquema de solicitud de inventario](../core/step-2-create-the-inventory-request-schema.md)   
 [Paso 4: Crear el mapa](../core/step-4-create-the-map.md)   
 [Paso 5: Generar el proyecto EAISchemas](../core/step-5-build-the-eaischemas-project.md)   
 [Crear esquemas con el Editor de BizTalk](../core/creating-schemas-using-biztalk-editor.md)