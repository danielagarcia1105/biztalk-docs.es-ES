---
title: Requisitos de PeopleSoft Enterprise | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PeopleSoft Enterprise, requirements
- send handlers, PeopleSoft requirements
- CLASSPATH environment variable
- custom component interface object
- system requirements
- GET_CI_INFO.pc
ms.assetid: fabd808d-d9b6-43b0-a12a-727189f00a9d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45f267afce09e9c50d732d376fde43beaa1ef39a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="peoplesoft-enterprise-requirements"></a>Requisitos de PeopleSoft Enterprise
## <a name="send-handler-peoplesoft-requirements"></a>Requisitos del controlador de envío de PeopleSoft  
 El adaptador de Microsoft BizTalk para PeopleSoft Enterprise contiene una interfaz de componente personalizado (CI) y proporciona acceso a ella a través de un API Java. Un objeto CI personalizado, `GET_CI_INFO`, se implementa en el sistema PeopleSoft mediante las herramientas de PeopleSoft, para proporcionar informar de metadatos, necesaria para el adaptador de BizTalk para PeopleSoft Enterprise. Para obtener más información, consulte [preparación para usar PeopleSoft Enterprise](../core/preparing-to-use-peoplesoft-enterprise.md).  
  
 La carga de la interfaz de componente personalizado es una única repetición. Este archivo, `GET_CI_INFO.pc`, se instala con el producto y debe instalarse antes de usar el adaptador para buscar CI. Es necesario tener acceso a PeopleSoft Application Designer, pero la aplicación Application Designer no tiene que estar necesariamente en el equipo de BizTalk Server. Use Application Designer para cargar el CI personalizado en el equipo de PeopleSoft en el que está buscando.  
  
 Debe tener acceso al equipo de PeopleSoft porque debe establecer la variable de entorno CLASSPATH (o establecer la información en el **propiedades de transporte** pantalla) para que señale a de PeopleSoft `PSJOA/psjoa.jar` archivo.  
  
## <a name="see-also"></a>Vea también  
 [Introducción](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   
 [Planeamiento y arquitectura](../core/planning-and-architecture13.md)