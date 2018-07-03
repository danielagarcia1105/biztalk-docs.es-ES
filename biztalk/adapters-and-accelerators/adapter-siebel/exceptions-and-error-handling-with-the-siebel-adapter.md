---
title: Excepciones y control de errores con el adaptador de Siebel | Microsoft Docs
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
ms.openlocfilehash: 67a615bec1bf1b8cd29e84728f39d6fea626f16e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977124"
---
# <a name="exceptions-and-error-handling-with-the-siebel-adapter"></a>Excepciones y control de errores con el adaptador de Siebel
## <a name="exception-list"></a>Lista de excepciones
Las excepciones producidas por la [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]. Estos pueden contener:  
  
- Una excepción interna, que es una excepción del sistema que se produce en .NET Framework  
  
- Una excepción de LOB que inicia la biblioteca de cliente de línea de negocio.  
  
  Para obtener más información acerca de la excepción interna, consulte la documentación de .NET Framework o Siebel respectiva. La excepción también contiene un mensaje de error detallado que ayuda a resolver el problema. Tenga en cuenta que la lista de excepciones que se mencionan aquí no es completa.  
  
|Excepción|Descripción de la posible causa/Error|  
|---------------|---------------------------------------|  
|ConnectionException|El adaptador produce esta excepción si no puede establecer una conexión o cerrar una conexión existente a un sistema Siebel.|  
|CredentialsException|El adaptador produce esta excepción si el cliente del adaptador no especifica un nombre de usuario o contraseña para conectarse a un sistema Siebel.|  
|MetadataException|El adaptador produce esta excepción si se produce un error al recuperar metadatos para artefactos de Siebel.|  
|XmlReaderParsingException|El adaptador produce esta excepción si la información de entrada proporcionada por los clientes del adaptador para invocar una operación en el sistema de Siebel, está incompleta o incorrecta.|  
|XmlReaderGenerationException|El adaptador produce esta excepción si no puede generar la salida para una operación que se ejecuta en un sistema Siebel.|  
|TargetSystemException|El adaptador produce esta excepción si la API de COM de Siebel, que el adaptador utiliza para interactuar con el sistema de Siebel, inicia una excepción. La excepción interna contiene la excepción producida por la API de COM de Siebel.|  
  
## <a name="see-also"></a>Vea también  
 [Comprender el adaptador de BizTalk para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)   
[Solucionar problemas del adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)