---
title: Excepciones y control de errores con el adaptador de Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error handling, troubleshooting
- exceptions, troubleshooting
- troubleshooting, exceptions and error handling
ms.assetid: d46e908f-0715-43e2-879b-f5d0beb9bc64
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 743e2a0f03e35282c24a506ff37e9d774f0b7505
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221868"
---
# <a name="exceptions-and-error-handling-with-the-siebel-adapter"></a>Excepciones y control de errores con el adaptador de Siebel
## <a name="exception-list"></a>Lista de excepciones
Las excepciones producidas por la [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]. Estos pueden contener:  
  
-   Una excepción interna, que es una excepción del sistema que se inicia de .NET Framework  
  
-   Una excepción de LOB que produce la biblioteca de cliente LOB.  
  
 Para obtener más información sobre la excepción interna, consulte la documentación de .NET Framework o Siebel respectiva. La excepción también contiene un mensaje de error detallado que le ayuda a resolver el problema. Tenga en cuenta que la lista de excepciones que se mencionan aquí no es completa.  
  
|Exception|Descripción de la posible causa/Error|  
|---------------|---------------------------------------|  
|ConnectionException|El adaptador produce esta excepción si no ha podido establecer una conexión o cerrar una conexión existente a un sistema Siebel.|  
|CredentialsException|El adaptador produce esta excepción si el cliente del adaptador no especifica un nombre de usuario o contraseña para conectarse a un sistema Siebel.|  
|MetadataException|El adaptador produce esta excepción si se produce un error al recuperar los metadatos de artefactos de Siebel.|  
|XmlReaderParsingException|El adaptador produce esta excepción si la información de entrada proporcionada por los clientes de adaptador para invocar una operación en el sistema Siebel, está incompleta o incorrecta.|  
|XmlReaderGenerationException|El adaptador produce esta excepción si no es capaz de generar una salida para una operación que se ejecuta en un sistema Siebel.|  
|TargetSystemException|El adaptador produce esta excepción si la API de COM de Siebel, que el adaptador utiliza para comunicarse con el sistema de Siebel, se producirá una excepción. La excepción interna contiene la excepción producida por la API de COM de Siebel.|  
  
## <a name="see-also"></a>Vea también  
 [Comprender el adaptador de BizTalk para Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)   
[Solucionar problemas del adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)