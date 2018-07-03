---
title: Trabajar con las directivas BRE | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BRE policies, about BRE policies
- BRE policies
ms.assetid: 4470f2b3-6891-46d7-9ba1-848f90d0767d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdb05d6f11d0d4d4f4ef5fd990d05c51b5e0df64
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968957"
---
# <a name="working-with-bre-policies"></a>Trabajar con las directivas BRE
Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] valida SWIFT directivas mensajes mediante el motor de reglas de negocios (BRE), como se describe en el *Guía de referencia de SWIFT*. Estas directivas incluyen lo siguiente:  

- Formato  

- Intervalo de valores  

- Entradas de la lista válida  

- Reglas de red con los códigos de error correspondiente  

- Reglas de uso que se pueden validar en el contenido del mensaje  

  Estas directivas no incluyen prácticas generales que no son dependientes en el contenido del mensaje o las validaciones entre mensajes.  

  El esquema XSD para el mensaje (y encabezado y finalizador) implementa opcionalidad básicas del campo y la cardinalidad, mientras que el esquema de mensaje que implementa el esquema de SWIFT Base Types.xsd de referencias de formato. Dos directivas específicas para cada tipo de mensaje definen las reglas asociadas con cada mensaje:  

- Directiva maestra (MT*xxx*_Master_Policy.xml)  

- Directiva de validación (MT*xxx*_Validation_Policy.xml)  

  La directiva principal para cada tipo de mensaje invoca las directivas específicas que se aplican a ese tipo de mensaje. Estas directivas específicas incluyen especial campo comprueba las funciones comunes implementan reglas de red y reglas de uso. La directiva principal para el mensaje es la primera directiva de ejecución para ese mensaje. La lista de directivas incluye la directiva de validación para el tipo de mensaje. Cada directiva maestra tiene la construcción "si escribe este mensaje, a continuación, ejecutar la lista de directivas".  

  La directiva de validación para cada tipo de mensaje enumera las comprobaciones de campo único que implementan otras reglas externos, como los códigos de campo, o usa un vocabulario específico para el campo. Estas reglas individuales son generalmente más comunes en dos o más mensajes, porque son específicos de los campos. El A4SWIFT_Codelists en el vocabulario BRE, código, de la programación no proporcionan los valores de permitido para el campo.  

  El *Guía de referencia de SWIFT* implementa cada una de las reglas de red de forma independiente. Cada regla de red trata el conjunto de tipos de mensaje que el *Guía de referencia de SWIFT* define.  

  Instalación de A4SWIFT no instala las reglas cuando instala A4SWIFT. Después de seleccionar los esquemas y generar e implementar un ensamblado, puede usar la utilidad de implementación de BRE para seleccionar e implementar las reglas adecuadas para el conjunto de esquemas. Para implementar las reglas para los mensajes seleccionados, ejecute la utilidad y seleccione los ensamblados correspondientes. La herramienta selecciona las correspondientes directivas maestras, las directivas de validación y cualquier red que se hace referencia u otras reglas.  

  A4SWIFT asocia los dos tipos de vocabularios con reglas de A4SWIFT. El primer vocabulario es A4SWIFT_Codelist, que contiene los distintos valores de la lista de código. El segundo vocabulario es A4SWIFT_Functions. Estos los vocabularios son [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] clases para las validaciones de lógica y los cálculos.  

  Puede invocar las reglas en una canalización de recepción, el Desensamblador de A4SWIFT estableciendo el parámetro de configuración de validación del BRE en true. También puede invocar las reglas de una orquestación. No se puede invocar las reglas por el ensamblador de A4SWIFT (ASM). Debe utilizar una orquestación o canalización de recepción para validar la instancia con respecto al esquema e invocar las reglas.  

  Si se produce un error en un mensaje de validación del esquema o una regla de negocios, A4SWIFT prepara una colección de errores que contiene una descripción de los errores detectados y una indicación de que el campo de error o la posición en el mensaje donde se produjo el error. Para obtener más información, consulte [trabajar con suscripciones de mensajes de error](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).  

  Puede agregar reglas adicionales para el conjunto de A4SWIFT. Por ejemplo, si adopta una regla de grupo de prácticas de mercado que afecta a un nuevo conjunto de mensajes, puede implementar una nueva versión de la directiva principal que incluye uno o más validaciones nuevo, según sea necesario. De forma similar, si se imponen comprobaciones adicionales de campo único, puede agregar estas comprobaciones a una nueva versión de la directiva de validación de mensajes. Puede implementar la validación nuevo como una nueva regla o como una función de vocabulario.  

  Esta sección contiene:  

- [Habilitación de la validación de códigos de identificación bancaria](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)  

- [Administración de la tabla Bicplus en la base de datos de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)  

- [Admitir ceros a la izquierda en validaciones de campos de cantidad](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md)  

- [Configuración de desplazamientos para la validación de cantidades](../../adapters-and-accelerators/accelerator-swift/setting-offsets-for-amount-validation.md)  

- [Eliminación de la validación de reglas de uso](../../adapters-and-accelerators/accelerator-swift/removing-usage-rule-validation.md)
