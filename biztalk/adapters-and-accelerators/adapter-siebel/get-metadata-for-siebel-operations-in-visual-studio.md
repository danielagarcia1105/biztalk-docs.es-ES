---
title: Obtener metadatos para operaciones de Siebel en Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving for Siebel operations in Visual Studio
ms.assetid: 63643942-6497-4891-ad7d-34b1df9acbc1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b4a7b6ed8cfd678d725323d92de045d27e10085
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014541"
---
# <a name="get-metadata-for-siebel-operations-in-visual-studio"></a>Obtener metadatos para operaciones de Siebel en Visual Studio
El [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] proporciona dos [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes que puede usar para desarrollar soluciones mediante el adaptador.  
  
- El [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] está disponible en proyectos de BizTalk Server. Usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar esquemas (XSD) de mensaje para las operaciones que desee establecer como destino en la solución de BizTalk. Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, consulte [aplicaciones de desarrollo de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md).
  
- El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] está disponible en proyectos de programación que no sean de BizTalk. Usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una clase de cliente WCF o una interfaz de devolución de llamada de servicio WCF cuando se desarrollan soluciones mediante el modelo de servicio WCF. Para obtener más información sobre cómo desarrollar soluciones con el modelo de servicio WCF, vea [Siebel desarrollar las aplicaciones mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md).  
  
  Ambas opciones [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes simplifican el desarrollo mediante:  
  
- Proporcionar una interfaz de Microsoft Windows a través del cual puede examinar y buscar para las operaciones que desea usar en la solución.  
  
- Recuperar los metadatos expuestos por el adaptador para estas operaciones de destino.  
  
- Convertir los metadatos, que se expresa como un documento de lenguaje de descripción de servicios Web (WSDL) por el adaptador, en un formulario que puede usar en la solución (esquemas de mensaje XSD para los proyectos de BizTalk o una representación de objeto de .NET de un contrato de servicio de WCF modelo de servicio) y agregarlo al proyecto.  
  
  Esta sección proporciona instrucciones sobre cómo usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  

  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)