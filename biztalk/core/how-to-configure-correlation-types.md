---
title: Cómo configurar tipos de correlaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, correlation types
- correlation types, configuring
- correlation types, deleting
- configuring, correlation types
ms.assetid: cfae4d2e-ec79-45c8-93b3-799dc5e0576e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 646ac7dafd5207a2558e45252077efe2d9616a70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248572"
---
# <a name="how-to-configure-correlation-types"></a>Cómo configurar tipos de correlaciones
Usa el **propiedades de correlación** cuadro de diálogo para agregar o quitar propiedades de un tipo de correlación. El tipo de correlación enumera las propiedades de un conjunto de correlaciones que utilizan las actividades de envío y recepción para garantizar que los mensajes entrantes se correlacionan correctamente con las instancias correctas de una orquestación en tiempo de ejecución.  
  
 Hay dos paneles en el cuadro de diálogo, cada uno con una lista de propiedades. El panel izquierdo, "Propiedades disponibles", contiene una vista de árbol de todas las propiedades definidas en el proyecto o a las que se hace referencia en el mismo. Las propiedades que aparecen de forma predeterminada son propiedades del sistema, definidas por BizTalk Server, aunque también puede definir sus propias propiedades en un esquema de propiedades. Para obtener más información acerca de cómo crear esquemas de propiedades, vea [esquemas de propiedades](../core/property-schemas.md).  
  
> [!NOTE]
>  Las propiedades de esquema deben estar promocionadas antes de poder usarlas en un tipo de correlación. Para obtener más información, consulte [promocionar propiedades](../core/promoting-properties.md).  
  
### <a name="to-add-and-configure-a-correlation-type"></a>Para agregar y configurar un tipo de correlación  
  
-   En la ventana Vista orquestación, haga clic en **tipos de correlaciones** y, a continuación, haga clic en **nuevo tipo de correlación**.  
  
     El **propiedades de correlación** aparece el cuadro de diálogo. Agregue las propiedades que desee incluir en el tipo de correlación.  
  
    > [!NOTE]
    >  Si tiene acceso a la **propiedades de correlación** cuadro de diálogo directamente desde una correlación del conjunto, se crea un tipo de correlación para el conjunto de correlaciones si no existe. Los cambios realizados se guardarán en el nuevo tipo de correlación, y se configurará el conjunto de correlaciones para que utilice este nuevo tipo. Si el tipo de correlación ya existe en el conjunto de correlaciones y realiza algún cambio, se modificará el tipo de correlación.  
  
### <a name="to-remove-a-correlation-type"></a>Para quitar un tipo de correlación  
  
-   En la ventana Vista orquestación, haga clic en el tipo de correlación que desee quitar y, a continuación, haga clic en **eliminar**.