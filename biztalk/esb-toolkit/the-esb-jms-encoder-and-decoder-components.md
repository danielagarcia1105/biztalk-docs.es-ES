---
title: El codificador de ESB JMS y componentes de descodificador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e5591c2-d2ca-4168-8026-059fe51dd588
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f39f4ab1b0650a8ad6fa1ff35d62b4807995237
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-jms-encoder-and-decoder-components"></a>El codificador de ESB JMS y componentes de descodificador
Algunas soluciones de integración implican Java Message Service (JMS) y los mensajes SOAP enviados a o desde IBM WebSphere MQ; [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye dos componentes de canalización JMS escritos en código administrado para su uso en estas situaciones. Los componentes de leen o escribir la parte JMS del encabezado del mensaje MQ mediante los valores de propiedades de contexto asociados con el mensaje. Actualmente, hay más de 60 tipos diferentes de los encabezados JMS en uso con sistemas de WebSphere MQ Series; los componentes de ESB JMS solo funcionan con encabezados de MQRFH2.  
  
## <a name="installation"></a>Installation  
 Instalar automáticamente el núcleo de ESB instala los componentes de JMS codificador y descodificador de JMS en la carpeta de componentes de canalización de BizTalk Server.  
  
## <a name="how-it-works"></a>Funcionamiento  
 Los componentes de canalización JMS inspeccionar los encabezados del mensaje y sólo funcionan en los mensajes que tienen la **MQMD_Format** encabezado establecido en **RFH (MQRFH2)**. Sin embargo, incluso cuando se establece esta propiedad, los componentes de inspeccionar los encabezados para confirmar que se ajustan al formato IBM RFH2. Si el encabezado no se ajusta a este formato, los componentes de generan un error de análisis que indica la **MQMD_Format** parámetro se estableció en **RFH (MQRFH2)**, pero la estructura del encabezado no cumplía con el estándar RFH2. Si se produce un error de análisis de encabezado de mensaje entrante, el componente descodificador permite que pase el mensaje, pero establece una propiedad de contexto de mensaje denominada **MQRFH2_ParseError** a **True**.  
  
 El **MQRFH2** esquema de propiedad que se implementa en BizTalk con los componentes JMS expone todas las propiedades de encabezado MQRFH2. Después de degradar los encabezados de un mensaje entrante, los datos de los encabezados residen en un documento XML almacenado en el **MQRFH2_NameValueData** propiedad de contexto del mensaje. El codificador ajusta la longitud de la **NameValueData** carpeta para asegurarse de que es la longitud correcta. Para entender el uso de estos encabezados y el impacto al cambiar los valores, consulte la documentación de IBM adecuada.  
  
## <a name="using-the-jms-encoder-and-decoder-components"></a>Usar el codificador JMS y componentes de descodificador  
 Para usar los componentes de JMS codificador y descodificador, los desarrolladores de agregarlos a canalizaciones en una aplicación de BizTalk. Para una canalización de envío, el componente de codificador de JMS debe residir en la fase de codificación. Para una canalización de recepción, el componente de descodificador de JMS debe residir en la fase de descodificación. No se instalarán los componentes JMS en las otras fases de una canalización.  
  
 Cuando se instalan en la fase de codificación, el componente de codificador de JMS lee los valores de la JMS **MQRFH2** encabezados y escrituras (promociona) en las propiedades de contexto de mensaje. Cuando se instalan en la fase de descodificación, lee el componente de descodificador de JMS (degrada) la propiedad de contexto valores y los inserta en la JMS **MQRFH2** encabezados. Esto significa que todos los valores de encabezado MQ están disponibles como propiedades de contexto del mensaje en la canalización.  
  
 Para detectar y administrar los errores de análisis de encabezado, los desarrolladores pueden incluir código que examina el valor de la **MQRFH2_ParseError** propiedad. Puede implementar un proceso de recuperación que se suscribe a mensajes con errores o especificar puertos de envío que filtrar en el **MQRFH2_ParseError** propiedad para conservar el mensaje. Los suscriptores que funcionan con los mensajes JMS deben incluir una condición de filtro que especifica el valor **False** para el **MQRFH2_ParseError** propiedad para evitar que el suscriptor recibe los mensajes que Error en el encabezado del proceso de análisis.  
  
 Los desarrolladores también pueden actualizar los valores de propiedad de contexto (por ejemplo, cambiar el **MQRFH2_Encoding** valor de propiedad), y el componente reflejará los cambios en los encabezados del mensaje MQ para que se establecen cuando el mensaje llega a su destino final. El componente automáticamente omite los valores no válidos y establece los valores predeterminados "seguros" donde faltan encabezados necesarios. Por ejemplo, si el programador especifica un valor no válido para la **MQRFH2_Encoding** propiedad, el mensaje de salida tendrá el **MQRFH2_Encoding** encabezado establecido en **desconocido**. Si el programador quita un valor de una propiedad de contexto, pero la **MQMD_Format** propiedad todavía está establecida en **RFH**, el componente agregará un encabezado que contiene el valor predeterminado, según la especificación de IBM.  
  
 Para obtener un ejemplo de cómo usar estos componentes, consulte [instalar y ejecutar el ejemplo de componente de JMS MQRFH2](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md).