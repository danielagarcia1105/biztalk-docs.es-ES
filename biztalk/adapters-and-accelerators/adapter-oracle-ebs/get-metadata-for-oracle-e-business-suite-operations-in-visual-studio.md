---
title: Obtener metadatos para operaciones de Oracle E-Business Suite en Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87d7f731-cd0f-4970-a3cd-072f09312989
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f4a7b5d016adf1cc7fa8bb73772e1e5d7145520
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002077"
---
# <a name="get-metadata-for-oracle-e-business-suite-operations-in-visual-studio"></a>Obtener metadatos para operaciones de Oracle E-Business Suite en Visual Studio
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] proporciona tres [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes que puede usar para ayudar a desarrollar soluciones con el adaptador:  
  
- [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]  
  
- [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]  
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]  
  
  Los clientes del adaptador deben usar estos componentes para conectarse a Oracle E-Business Suite y, a continuación, generar los metadatos para las operaciones que desean realizar. Todos estos [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes simplifican el desarrollo mediante:  
  
- Proporcionar una interfaz de Microsoft Windows a través del cual puede examinar y buscar para las operaciones que desea usar en la solución.  
  
- Recuperar los metadatos expuestos por el adaptador para estas operaciones de destino.  
  
- Convertir los metadatos, que se expresa como un documento de lenguaje de descripción de servicios Web (WSDL) por el adaptador, en un formulario que puede usar en la solución (esquemas de mensaje XSD para los proyectos de BizTalk o una representación de objeto de .NET de un contrato de servicio de WCF modelo de servicio) y agregarlo al proyecto.  
  
  Esta sección proporciona instrucciones sobre cómo usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
> [!NOTE]
>  Si ha creado una solución mediante el adaptador en una versión determinada de Oracle E-Business Suite y ahora desea implementar la solución en una versión diferente de Oracle E-Business Suite, a continuación, debe probar la solución antes de implementarla. Que se produzcan problemas al implementar la solución en una versión diferente de Oracle E-Business Suite, porque los metadatos del artefacto subyacente pueden ser diferente. Para resolver este problema, debe volver a generar los metadatos mediante el adaptador en la misma versión de Oracle E-Business Suite en el que va a implementar la solución.  
  
