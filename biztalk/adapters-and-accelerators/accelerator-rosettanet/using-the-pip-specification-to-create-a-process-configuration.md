---
title: "Mediante la especificación de PIP para crear una configuración de proceso | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PIPs, PIP settings
- PIPs, PIP secifications
- process configuration, PIPs
- PIPs, process configuration
ms.assetid: 64f0f5fb-f880-4ef1-95d7-2575b8d0bcff
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 777f32e5a9e035f6009f5450eb48ae8286159f05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-pip-specification-to-create-a-process-configuration"></a>Mediante la especificación de PIP para crear una configuración de procesos
Después de descargar un proceso de interfaz de socio (PIP) de la organización RosettaNet (en RosettaNet.org), el paquete de descarga incluye un documento de especificación de PIP. Este documento contiene instrucciones sobre la configuración que desea usar al crear una configuración de procesos en el [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] consola de administración.  
  
## <a name="how-pip-settings-map-to-the-pip-specification"></a>PIP cómo se asignan valores a la especificación de PIP  
 En la tabla siguiente describe cómo se asignan los valores de PIP a la información de la especificación de PIP de RosettaNet.  
  
|Configuración de proceso|Información de la especificación de PIP|  
|-----------------------------------|------------------------------------------|  
|Código de proceso|Subtítulo en la página de título, por ejemplo, "PIP3A4"|  
|Versión|Subtítulo de identificador de la versión PIP en la página de título, por ejemplo, "02.02.00"|  
|Nombre del proceso|Subtítulo en la página de título, por ejemplo, "solicitud de pedido de compra"|  
|Descripción (pestaña General)|Sección 3.1, definición de procesos de negocios|  
|Se necesita la propiedad Sin repudio|Controles de rendimiento de actividad de negocio de tabla 3-3:|  
|Tiempo de confirmación (segundos)|Controles de rendimiento de actividad de negocio de tabla 3-3:|  
|¿Se requiere una autorización?|Controles de rendimiento de actividad de negocio de tabla 3-3:|  
|Se necesita confidencialidad persistente|(Ninguna referencia de la especificación de PIP)|  
|¿Es necesario el transporte seguro?|Controles de cambio de la tabla 4-3: mensaje|  
|Es de una sola acción|La sección 4.3, la especificación de cuadro de diálogo de transacciones de negocio|  
|Sin repudio del origen y del contenido|Controles de rendimiento de actividad de negocio de tabla 3-3:|  
|Número de reintentos|Controles de rendimiento de actividad de negocio de tabla 3-3:|  
|Tiempo de ejecución|Controles de rendimiento de actividad de negocio de tabla 3-3:|  
|Nombre|Tabla 3-3: Business actividad rendimiento controles (nombre de la actividad)|  
|Tipo|(Ninguna referencia de la especificación de PIP - para un uso futuro)|  
|Descripción (pestañas de iniciador y respuesta)|Documentos empresariales PIP de tabla 3-4:|  
|Nombre (pestañas de iniciador y respuesta)|Documentos empresariales PIP de tabla 3-4:|  
|Rol (pestañas de iniciador y respuesta)|Descripciones de rol de asociado de tabla 3-1:|  
|Descripción del rol (pestañas de iniciador y respuesta)|Descripciones de rol de asociado de tabla 3-1:|  
|Tipo de función (pestañas de iniciador y respuesta)|Descripciones de rol de asociado de tabla 3-1:|  
|ssNoVersion|Especificaciones del componente de red de la tabla 4-1:|  
|Clasificación de servicios|Especificaciones del componente de red de la tabla 4-1:|  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)