---
title: Admite los tipos de columna de Windows SharePoint Services | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Windows SharePoint Services adapters], supported column types
- Windows SharePoint Services adapters, supported column types
ms.assetid: 14992f52-9d18-4321-9152-83c8a37751bc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5328c5dade3f02c480b58c36ff2cfdf9a5e7493
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278876"
---
# <a name="supported-windows-sharepoint-services-column-types"></a>Tipos admitidos de columna de Windows SharePoint Services
En este tema se describen los tipos de columna de Windows SharePoint Services que admite el adaptador de Windows SharePoint Services. Los valores de estos tipos de columna pueden establecerse en el mensaje.  
  
> [!NOTE]
>  El adaptador no actualiza columnas calculadas.  
  
## <a name="supported-types"></a>Tipos admitidos  
 En la tabla siguiente se describen los tipos de columna admitidos:  
  
|Tipo de UI|Tipo de modelo de objetos de SharePoint|Ejemplo|Comentarios|  
|-------------|----------------------------------|------------|--------------|  
|Una línea de texto|SPFieldType.Text|Una línea|Ninguno|  
|Varias líneas de texto|SPFieldType.Note|línea 1<br /><br /> línea 2<br /><br /> línea 3|Ninguno|  
|Lista desplegable de opciones|SPFieldType.Choice|ChoiceA|ChoiceA de entre las opciones disponibles (ChoiceA, ChoiceB y ChoiceC)|  
|Botones de opción|SPFieldType.Choice|#ChoiceB;#ChoiceC;#|Se habilitan ChoiceB y ChoiceC, mientras que ChoiceA se deshabilita (las opciones disponibles son ChoiceA, ChoiceB y ChoiceC). Utilice ;# como separador.|  
|Number|SPFieldType.Number|123.456|Ninguno|  
|Moneda USD (o cualquier otra)|SPFieldType.Currency|100.00|Ninguno|  
|Lookup|SPFieldType.Lookup|1|El número es el identificador de elemento que se encuentra dentro de la lista a la que se hace referencia.|  
|SíNo|SPFieldType.Boolean|1|1=Sí<br /><br /> 0=No|  
|Hipervínculo o imagen|SPFieldType.URL|http://www.microsoft.com, Sitio Web de Microsoft|La dirección URL se separa del texto mostrado mediante ",". El texto "Sitio Web de Microsoft" será un hipervínculo que llevará a http://www.microsoft.com.|  
|Fecha y hora|SPFieldType.DateTime|2005-02-11T10:05:04|DateTime, tal como lo define el estándar XML para xs:dateTime. El patrón para dateTime es SSAA-MM-DDThh:mm:ss, donde SS representa el siglo, AA el año, MM el mes y DD el día, precedido por un carácter negativo (-) opcional a la izquierda para indicar un número negativo. Si se omite el carácter negativo, se da por hecho el positivo (+). La T es el elemento separador de la fecha y la hora; por lo demás, hh, mm y ss representan, respectivamente, horas, minutos y segundos. Inmediatamente después de esta representación, puede aparecer una "Z" para indicar la hora UTC o la zona horaria.|  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar Windows SharePoint Services ubicación de recepción](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [Cómo configurar un controlador de envío de Windows SharePoint Services](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [Cómo configurar un puerto de envío de Windows SharePoint Services](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [Cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md)   
 [Referencia de propiedades de adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [Expresiones del adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-expressions.md)