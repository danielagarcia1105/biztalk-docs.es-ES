---
title: Excepciones y control de errores con el adaptador de la base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exception, LOB
- exception, inner
- exceptions, error handling
- error handling, exceptions
ms.assetid: df9a1244-63cd-438e-8a06-99383fbeba2c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bd85c53a1e13d127883e463cafec742f2751722
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215172"
---
# <a name="exceptions-and-error-handling-with-the-oracle-database-adapter"></a>Excepciones y control de errores con el adaptador de la base de datos de Oracle
Esta sección enumeran las excepciones que el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] produce. Estos pueden contener:  
  
-   Una excepción interna, que es una excepción del sistema que se inicia de .NET Framework.  
  
-   Una excepción de LOB que produce la biblioteca de cliente LOB.  
  
 Para obtener más información sobre la excepción interna, consulte la documentación de .NET Framework u Oracle respectiva. Las excepciones también contienen un mensaje de error detallado que le ayuda a resolver el problema.  
  
|Exception|Posible causa/descripción|  
|---------------|---------------------------------|  
|XmlReaderParsingException|El adaptador produce esta excepción si no es compatible con el tipo especificado, o si se especifica un valor incorrecto para el tipo. Además, el XML de entrada puede ser incorrecto. Un valor incorrecto incluye los casos donde se supera la cantidad máxima de texto o el número máximo de dígitos. El XML de entrada puede ser incorrecto si el nombre de la operación o el espacio de nombres es incorrecto.|  
|Excepción UnsupportedOperationException|El adaptador produce esta excepción cuando el cliente de adaptador especifica una acción no válida.|  
|ArgumentException|El adaptador produce esta excepción si se especifica un valor incorrecto para un argumento.|  
|NotImplementedException|El adaptador produce esta excepción si no se implementa algún método del lector de XMLReader.|  
|ArgumentNullException|El adaptador produce esta excepción si no se especifica un argumento requerido.|  
|ArgumentOutOfRangeException|El adaptador produce esta excepción si intenta obtener acceso a una entidad no existente o una entidad de fuera de intervalo.|  
|XmlReaderGenerationException|El adaptador produce esta excepción cuando no es capaz de generar un objeto XmlReader desde el mensaje de salida.|  
|MetadataException|El adaptador produce esta excepción si se produce un error durante la recuperación de metadatos, examinar o buscar.|  
|CredentialsException|El adaptador produce esta excepción si se produce un problema al recuperar o el uso de tokens de seguridad o si no se especifican las credenciales necesarias.|  
|InvalidUriException|El adaptador produce esta excepción si el URI de conexión no tiene los componentes necesarios para la cadena de conexión.|  
|ConnectionException|El adaptador produce esta excepción si hay un problema al conectarse a la base de datos de Oracle mediante ODP.NET. La excepción interna contiene la excepción de Oracle.|  
|TimeoutException|El adaptador produce esta excepción si el tiempo de espera especificado para una operación está vencido. La excepción interna contiene los detalles de por qué el tiempo de espera especificado no era suficiente.|  
|ListenerException|El adaptador produce esta excepción si hay un problema en recibir un mensaje desde el sistema de destino. Este mensaje indica un problema relacionado con el agente de escucha de Oracle. La excepción interna tiene los detalles del problema.|  
|TargetSystemException|El adaptador produce esta excepción si Oracle devuelve un error o una respuesta no válida. La excepción interna contiene la excepción de tiempo de ejecución de Oracle.|  
|InvalidOperationException|El adaptador produce esta excepción si el adaptador intenta realizar una operación no válida en el sistema de destino. La excepción interna contiene los detalles de la operación no válida que se está realizando.|  
|OverflowException|El adaptador produce esta excepción si al realizar la operación que contiene los tipos de datos numéricos de Oracle dentro de los conjuntos de datos o débilmente tipada cursores REF CURSOR, se especifica un valor grande para estos tipos de datos numéricos de Oracle que no caben en el tipo de .NET correspondiente.|  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)