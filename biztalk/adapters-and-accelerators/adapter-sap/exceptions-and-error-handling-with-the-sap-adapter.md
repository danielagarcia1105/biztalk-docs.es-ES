---
title: Excepciones y control de errores con el adaptador de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions and error handling
- error handling, troubleshooting
- troubleshooting, exceptions and error handling
ms.assetid: 598a25c5-6905-4c0c-835b-159d827b2269
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5439ae9cc58dfbb649fefd7ae3f18348502bcd48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991629"
---
# <a name="exceptions-and-error-handling-with-the-sap-adapter"></a>Excepciones y control de errores con el adaptador de SAP
Se muestran las excepciones que el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] produce. Estos pueden contener:  

- Una excepción interna, que es una excepción del sistema que se produce en .NET Framework  

- Una excepción de LOB que inicia la biblioteca de cliente de línea de negocio.  

  Para obtener más información acerca de la excepción interna, consulte la documentación de .NET Framework o SAP. Las excepciones también contienen un mensaje de error detallado que puede ayudar a resolver el problema.  

## <a name="exception-descriptions"></a>Descripciones de excepción  

|Excepción|Posible causa/descripción|  
|---------------|---------------------------------|  
|ObjectDisposedException|El adaptador produce esta excepción cuando el cliente de adaptador está intentando obtener acceso a la respuesta XMLReader después de que se ha eliminado.|  
|XmlReaderGenerationException|El adaptador produce esta excepción cuando no puede generar un objeto XmlReader desde el mensaje de salida. Esto también podría ser debido a algunos problemas relacionados con los datos recibidos desde el sistema SAP. Busque la excepción interna y el mensaje de error para obtener más información.|  
|InvalidUriException|Esta excepción se produce cuando el URI de conexión no tiene los componentes necesarios para la cadena de conexión.|  
|ConnectionException|Esta excepción se produce cuando hay un problema al conectarse al sistema SAP o si una conexión subyacente deja de ser válida, debido a un error en el sistema SAP o debido a un problema de red.|  
|TimeoutException|Esta excepción se produce cuando el tiempo de espera especificado para una operación está vencido. La excepción interna contiene los detalles de por qué el tiempo de espera especificado no era suficiente.|  
|XmlReaderParsingException|El adaptador produce esta excepción si no admite el tipo especificado, o si se especifica un valor incorrecto para el tipo. Además, el XML de entrada puede ser incorrecto. Un valor incorrecto incluye los casos donde se supera la cantidad máxima de texto o el número máximo de dígitos. El XML de entrada puede ser incorrecto si el nombre de la operación o el espacio de nombres es correcto.|  
|RFCException (derivado de AdapterException)|El adaptador produce esta excepción si se produce un error recibido desde el sistema SAP. La excepción interna es la excepción real recibida desde el sistema SAP.|  
|Excepción UnsupportedOperationException|El adaptador produce esta excepción cuando el cliente de adaptador especifica una acción no válida.|  
|MetadataException|El adaptador produce esta excepción si se produce un error durante la recuperación de metadatos, examinar o buscar.|  

## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador SAP](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)