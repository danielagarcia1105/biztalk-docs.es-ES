---
title: Comprender el sistema LOB con el SDK de adaptador LOB de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0f97846-5ef2-4530-853a-fba5469156f7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a3cb898643e8a7eff1b73a138f98f1ecfc05248
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993133"
---
# <a name="understand-the-lob-system-with-the-wcf-lob-adapter-sdk"></a>Comprender el sistema LOB con el SDK de adaptador LOB de WCF
Antes de desarrollar el adaptador mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], debe tener una explicación exhaustiva sobre el sistema de línea de negocio de destino. Si no comprende la funcionalidad proporcionada por el sistema de línea de negocio, cómo se expone y el nivel de soporte técnico proporcionado por seguridad, transacciones y otras características diferentes, el adaptador no puede proporcionar las características necesarias para el adaptador consumidores. Esta sección describen las áreas que debe comprender para diseñar el adaptador de forma eficaz.  
  
## <a name="the-path-to-understanding"></a>Para familiarizarse con la ruta de acceso  
 El propósito de un adaptador es exponer los datos y las operaciones de un sistema de línea de negocio de una manera coherente y accesible según las reglas impuestas por la especificación de adaptador o la API del adaptador. Para saber qué operaciones y los datos para exponer, debe entender lo que hace el sistema y cómo lo expone sus datos y las operaciones. En concreto, debe pensar en los siguientes problemas de diseño:  
  
- **Ciclo de vida de la conexión.** ¿Cómo se abren y se cierran de conexiones? ¿Cómo son las conexiones abiertas mantenidas? ¿Existen requisitos especiales para volver a usar una conexión? Para obtener más información acerca de las conexiones, consulte `Microsoft.ServiceModel.Channels.Common.IConnection`.  
  
- **Los metadatos de operación y el tipo expuestos por el sistema.** ¿El sistema de línea de negocio admite búsqueda de la operación y examinar y facilitar el acceso a los metadatos, o debe desarrollar código de soporte técnico para proporcionar esta funcionalidad? Por ejemplo, en SQL Server, las operaciones son objetos de procedimientos almacenados, como. Son fáciles de recuperar metadatos sobre las columnas, tablas y otros objetos. Sistemas heredados de línea de negocio pueden ser más difíciles trabajar con.  
  
- **Cómo se exponen las operaciones y los datos por el sistema.** ¿Cómo se expone la API? ¿Realiza la compatibilidad con la API de bloqueo (sincrónico) y sin bloqueo (asincrónicas) llamadas? ¿Se admiten las devoluciones de llamada? ¿Se comunicará en el nivel de protocolo o la API?  
  
- **Compatibilidad con seguridad, transacciones y la mensajería de confianza.** Si la API es compatible con cualquiera de estas características, es posible que desean exponerlos al consumidor de adaptador. Por ejemplo, SQL Server tiene la seguridad y transacciones admiten aunque la mensajería de confianza no resulta práctica (pero sería con MSMQ o algún otro sistema de puesta en cola).  
  
- **¿Qué escenarios de uso y la funcionalidad están tan importantes?** No existe límite en sus conocimientos a puramente técnico; Comente y capturar los requisitos de negocio con los usuarios con experiencia. ¿Existen restricciones únicas impuestas en algunas operaciones? ¿Son hay operaciones que son poco claros todavía útiles? ¿Algunas funciones rara vez se usan?  
  
  Para conocer esta información, deben consultar el usuario y la documentación técnica para el sistema de línea de negocio de destino. Si la documentación es dispersa o que faltan, también puede obtener información sobre los aspectos técnicos del sistema mediante la búsqueda de foros de soporte técnico en línea, los grupos de noticias en línea, blogs, o mediante el examen de los archivos de instalación para obtener detalles de implementación. Si tiene acceso a la línea de negocio a los desarrolladores o los archivos de código, puede ser capaz de detectar la información que necesita incluido semántica de la conexión, compatibilidad con la seguridad y cómo se buscan y se invocan las operaciones.  
  
## <a name="see-also"></a>Vea también  
 [Planear y diseñar el adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)   
 [Introducción a la con el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md)   
 [Seleccione el marco adecuado](https://msdn.microsoft.com/library/bb798089.aspx)