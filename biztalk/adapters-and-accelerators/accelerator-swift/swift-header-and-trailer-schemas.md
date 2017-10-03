---
title: Esquemas de finalizador y encabezado SWIFT | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- trailer schemas
- schemas, headers
- schemas, trailers
- header schemas
ms.assetid: 82cd33d4-6bbb-4124-9506-fd35b5dca8a4
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8f3cb45e14a7c7e900fc26a4cbc8fcfb5d7b66e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="swift-header-and-trailer-schemas"></a>Esquemas de finalizador y encabezado SWIFT
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] proporciona SWIFT esquemas de encabezado y finalizador. A4SWIFT ya incorpora estos elementos en los esquemas de intercambio para los distintos mensajes FIN. Si desea crear un tipo de mensaje de estilo de formato de SWIFT FINÉS personalizado (por ejemplo, un mensaje de N98), puede incorporar los esquemas de encabezado y finalizador en su propio formato.  
  
 El esquema de encabezado SWIFT (SWIFT Header.xsd) contiene los formatos para lo siguiente:  
  
-   Encabezado básico  
  
-   Encabezado de la aplicación (opción de entrada o salida)  
  
-   Encabezado de usuario  
  
-   Delimitador de principio del bloque de texto  
  
 El encabezado básico contiene información sobre el origen del mensaje. El encabezado de la aplicación contiene información sobre el tipo de mensaje y el destino del mensaje. La resolución del tipo de mensaje el Desensamblador SWIFT en una canalización de recepción se basa en el contenido del campo en el encabezado adecuado de la aplicación. El encabezado de usuario es opcional y contiene las instrucciones de procesamiento especial.  
  
> [!NOTE]
>  Algunos tipos de mensajes tienen formatos variable según el contenido del campo 119 en el encabezado de usuario. Se trata de "tipos de mensaje dual" en A4SWIFT. El Desensamblador de A4SWIFT utiliza el tipo de mensaje en el encabezado de la aplicación junto con los contenidos del campo 119 para seleccionar el esquema adecuado para una instancia de mensaje.  
  
 El *manual de usuario de SWIFT*, que forma parte de la documentación para el servicio FIN, SWIFT describe todos estos encabezados.  
  
 El principio del bloque de texto es "{4:" seguido por un retorno de carro y avance de línea. Se requiere el principio del bloque de texto.  
  
 Con el fin de realizar un procesamiento (analizar y validar) de intercambios que contienen solo SWIFT bloque 4, todos los bloques de encabezado y finalizador en los esquemas de intercambio se marcan como opcionales. Esto se desvía de la especificación de SWIFT FINÉS, donde el bloque de encabezado básico 1 y el bloque de encabezado de la aplicación 2 son obligatorios. Esto le permite utilizar el esquema de intercambio para procesar los mensajes que no requieren encabezados. Por ejemplo, si se acepta mensajes recibidos a través de FileAct, el encabezado de lote puede contener el origen de los mensajes, así como un tipo de mensaje común.  
  
 El esquema de Common Language RunTime DLL también incluye el esquema de encabezado. Instalación de A4SWIFT implementa el esquema en tiempo de ejecución del archivo DLL y el esquema de propiedades de A4SWIFT. Si tiene que utilizar su propio encabezado para el procesamiento, puede definir e implementar un esquema de encabezado personalizado y promocionar las propiedades adecuadas para la resolución del mensaje. Si lo hace, también debe especificar el nuevo encabezado en el Desensamblador SWIFT (DASM). El esquema de encabezado personalizado no debe tener el mismo tipo de documento que el esquema de encabezado SWIFT esa instalación implementado en los esquemas en tiempo de ejecución del archivo DLL de A4SWIFT. No olvide cambiar el espacio de nombres de esquema, o el nombre del nodo raíz o ambos.  
  
 El esquema de finalizador de SWIFT (**Trailer.xsd SWIFT**) contiene el formato para lo siguiente:  
  
-   Delimitador final del bloque de texto  
  
-   Finalizadores de usuario (información de usuario y del sistema)  
  
-   Finalizadores de sistema  
  
 El delimitador final del bloque de texto es "-"}. El bloque de finalizador comienza con "{5:". El contenido del bloque de finalizador incluye información de usuario (suma de comprobación, autenticación de mensajes, autenticación propietario etc.) y de información del sistema (mensajes retrasada, referencia de mensajes, mensajes duplicados posibles y así sucesivamente). Finalizadores agregadas por SWIFT también proporcionan un bloque terceros, delimitado por "{S:". El *manual de usuario de SWIFT*, bajo "Descripción del servicio FINÉS", se describe detalladamente el contenido del bloque 5. A4SWIFT no valida el contenido del bloque S.  
  
 La interfaz FIN real o la red SWIFT anexa los finalizadores. Si un mensaje contiene un finalizador cuando A4SWIFT recibe el mensaje, A4SWIFT lleva a cabo el finalizador con el mensaje. A4SWIFT no genera un error si un mensaje no contenía un finalizador cuando A4SWIFT recibe el mensaje. Como con encabezados, todas las entradas de finalizador, incluidos los bloques de por sí mismos, son opcionales en A4SWIFT.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con esquemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)