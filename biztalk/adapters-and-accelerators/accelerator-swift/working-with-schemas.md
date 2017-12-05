---
title: Trabajar con esquemas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- developing, schemas
- schemas, developing
ms.assetid: 123c4b43-34e4-41c7-980d-5d518b1479c1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 404beaeb617f7a6c0c5e3fc4ddc40126e6b97990
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="working-with-schemas"></a>Trabajar con esquemas
Los esquemas que se proporcionan en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] son el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] representación XSD de la sociedad para mensajes FIN de telecomunicaciones financieros bancos vinculados (SWIFT) en todo el mundo. Cada tipo de mensaje tiene su propio esquema, incluida la SWIFT encabezado y finalizador SWIFT (formato de intercambio). Este esquema es suficiente para enviar o recibir un mensaje SWIFT. Estos esquemas son una combinación única de los registros delimitados y posicionales, lo que proporciona una representación XML detallada de las estructuras FIN de archivo sin formato.  
  
 Mayoría de los clientes SWIFT usa un subconjunto relativamente pequeño de los mensajes de FIN de SWIFT. Para implementar una solución para estos clientes, puede crear un proyecto de esquema de BizTalk (como se muestra en [módulo 2: agregar un nuevo proyecto de esquemas](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md) del tutorial de A4SWIFT). Agregue los esquemas de mensaje relevante (MT*xxx*.xsd) de \\\ programa Files\Microsoft BizTalk Accelerator para SWIFT \<versión\> MessagePack\SWIFT Messages\A4SWIFT-SRG\< versión\>\Category x\MT xyy directorio, donde x es el primer dígito del tipo de mensaje FIN y xyy es el tipo de mensaje de tres dígitos para el mensaje.  
  
 Puede agregar varios esquemas para el mismo proyecto. Para mantener la capacidad de administración, no debe agregar más de 20 esquemas de mensaje por proyecto. También debe agregar los esquemas de base y comunes para el proyecto. Si ya ha implementado los esquemas de base y común, debe hacer referencia a su ensamblado, en lugar de implementarlos. Esta sección describen estos esquemas. Los esquemas de mensaje están listos para usar que sea para mensajes enviados a la red SWIFT y mensajes recibidos de SWIFT.  
  
 Puede examinar el contenido de cada esquema SWIFT en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] mediante el Editor de esquemas. Todos los esquemas de intercambio de mensajes tienen la siguiente estructura común:  
  
-   Encabezados  
  
-   Texto del mensaje  
  
-   Finalizadores  
  
 Esta sección describen los esquemas de encabezado y finalizador. El texto del mensaje consta de la carga del mensaje FIN y contiene todos los campos de datos excepto los campos que contienen el remitente, el receptor y el tipo de mensaje. Estos tres campos se encuentran en la parte de encabezado. Algunos mensajes también contienen un encabezado opcional del usuario, que también puede proporcionar información de procesamiento.  
  
 Cada carga de mensaje FIN está formada por una serie de campos de una secuencia definida. Estos campos se ajustan a las siguientes reglas:  
  
-   Los campos pueden estar obligatorio u opcional dentro de la secuencia.  
  
-   Una secuencia puede contener subsecuencias y puede repetir una secuencia subcarpetas dentro de una secuencia.  
  
-   Puede usar un campo en varios tipos de mensaje.  
  
-   Dentro de un campo, puede haber elementos o subcampos. Un elemento o un subcampo puede ser comunes a varios campos.  
  
-   Un nodo de grupo representa cada secuencia repetida.  
  
-   Cada campo Sí habrá varios niveles nodal, cada uno de ellos se describe como un registro.  
  
-   Elementos de esquema representan sólo los subcampos de nivel más bajo.  
  
-   Los esquemas de base y comunes definen registros y elementos comunes.  
  
-   Los esquemas representan algunos campos en varios formatos (como campos de entidad). Los esquemas definen estos campos como campos de elección.  
  
-   Algunos campos tienen una limitada a conjuntos de valores. En su mayor parte, el esquema muestra estos valores. Definiciones de esquema también incluyen la validación del juego de caracteres.  
  
 Esta sección contiene:  
  
-   [Esquemas base y comunes](../../adapters-and-accelerators/accelerator-swift/base-and-common-schemas.md)  
  
-   [Esquemas de finalizadores y encabezados de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-header-and-trailer-schemas.md)  
  
-   [Convenciones de nomenclatura de esquemas de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-schema-naming-conventions.md)