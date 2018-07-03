---
title: Uso de las extensiones de herramientas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5613bf15-6c0a-4a82-b200-24d0801d7ece
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf8628ffdbbb2844c7ce8afff3dfe903d0723449
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992498"
---
# <a name="using-the-xml-tool-extensions"></a>Utilizar las extensiones de herramientas XML
Las extensiones de herramientas XML de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permiten realizar tareas en esquemas, asignaciones e instancias de mensajes. Utilice estas extensiones en el tiempo de diseño del entorno de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Puede llevar a cabo las siguientes tareas:  
  
- **Validar un esquema**. Esta operación valida un esquema EDI basado en reglas EDI. Para obtener más información, consulte [validar un esquema (EDI)](../core/validating-a-schema-edi.md).  
  
- **Validar una instancia de mensaje**. Esta operación valida un único conjunto de transacciones (sin intercambio ni encabezados de grupo) o un intercambio procesado por lotes completo con varios conjuntos de transacciones (con intercambio y encabezados de grupo). Para validar un intercambio sin procesar por lotes, es necesario quitar el intercambio y los encabezados de grupo de la instancia. Para obtener más información, consulte [Validar instancia (EDI)](../core/validating-an-instance-edi.md).  
  
- **Generar una instancia de mensaje**. Esta operación genera un intercambio procesado por lotes completo o un conjunto de transacciones sin intercambio ni encabezados de grupo. Debe especificar los separadores, identificadores y otros formatos usados para generar la instancia. Para obtener más información, consulte [generar una instancia (EDI)](../core/generating-an-instance-edi.md).  
  
- **Comprobar una asignación**. Esta operación genera un documento de salida (con datos ficticios) basado en un documento origen y una asignación. Para obtener más información, consulte [comprobar una asignación](../core/testing-a-map.md).  
  
- **Validar una asignación**. Esta operación genera un archivo que contiene el XSLT subyacente de la asignación y un archivo que contiene objetos de extensión. Para obtener más información, consulte [validar una asignación (EDI)](../core/validating-a-map-edi.md).  
  
  En BizTalk Server, estas extensiones funcionan en esquemas EDI, asignaciones e instancias de mensajes. Estas extensiones permiten trabajar de forma más eficaz con esquemas EDI, asignaciones e intercambios complejos.  
  
  El programa de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] habilita de forma predeterminada las extensiones de herramientas XML. Si hace doble clic en un esquema en el Explorador de soluciones de Visual Studio, el **extensiones de Editor de esquemas** propiedad del esquema se establece en **extensión del Editor de esquemas EDI**. Esto es necesario para que funcionen las extensiones de herramientas XML. Puede seleccionar otra extensión del editor de esquemas a la vez que deja seleccionadas las extensiones EDI.  
  
## <a name="see-also"></a>Vea también  
 [Generar una instancia (EDI)](../core/generating-an-instance-edi.md)   
 [Validar una instancia (EDI)](../core/validating-an-instance-edi.md)   
 [Validar un esquema (EDI)](../core/validating-a-schema-edi.md)   
 [Comprobar una asignación](../core/testing-a-map.md)   
 [Validación de una asignación (EDI)](../core/validating-a-map-edi.md)