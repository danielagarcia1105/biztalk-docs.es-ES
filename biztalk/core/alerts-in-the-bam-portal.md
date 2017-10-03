---
title: Alertas del Portal de BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM portal, alerts
- alerts, summaries
- subscriptions, alerts
- alerts, details
- Alert Management page [BAM portal]
- alerts, subscriptions
ms.assetid: 715a4187-aafa-46be-8b00-8eaba2e569e5
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb94ad682eafec00d1947e795887a16dafb9d11f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="alerts-in-the-bam-portal"></a>Alertas del portal de BAM
Las alertas le permiten definir eventos importantes acerca de su proceso empresarial, como los indicadores clave de rendimiento (KPI) que se pueden entregar a usuarios en tiempo real. Los usuarios se suscriben a alertas para recibir notificaciones del evento empresarial que supervisa la alerta.  
  
 Por ejemplo, en vez de esperar a ver un informe después de que haya pasado un evento clave, BAM le reenvía la información a través de correo electrónico o de un archivo guardado en una ubicación conocida que se puede recoger mediante programación y que se le puede entregar de formas diferentes.  
  
## <a name="types-of-alerts-and-how-they-are-delivered"></a>Tipos de alertas y modos de entrega  
 Existen dos tipos de alertas, agregada e instancia. Una alerta agregada le permite determinar los datos de umbral a través de un marco de tiempo, mientras que un alerta de instancia se basa en puntos de datos necesarios determinados.  
  
 Las alertas se entregan de una de las dos maneras siguientes: mediante un mensaje de correo electrónico a los suscriptores, o como un archivo que se escribe a una ubicación determinada del sistema. Un alerta de correo electrónico tiene una línea de asunto que corresponde con el nombre de la alerta. El cuerpo del mensaje tiene definido el texto del mensaje para la alerta y un vínculo a la página de resultados del portal de BAM asociada a la alerta.  
  
## <a name="the-alert-management-page"></a>La página Administración de alertas  
 La página Administración de alertas se divide en tres áreas, como se muestra a continuación:  
  
### <a name="alert-summary"></a>Resumen de alertas  
 El **resumen de alertas** área del marco de contenido de administración de alertas muestra una lista de las alertas configuradas. En la cuadrícula de resumen se incluye información acerca de la alerta. Si hace clic en el resumen de alertas, se cargarán los detalles de la alerta en el área Detalles de alertas del marco de contenido. Puede usar esta información para determinar si la alerta satisface las necesidades y si desea suscribirse a ella.  Si es propietario de una alerta, puede editarla y guardarla. En la tabla siguiente se enumera la información general sobre la alerta.  
  
|Columna de resumen|Contenido|  
|--------------------|--------------|  
|Nombre|Nombre de la alerta.|  
|Tipo|Puede ser Agregada o Individual.|  
|Habilitado|Indica si la alerta está activa y si se puede generar.|  
|Prioridad|Indica la gravedad del problema que comunica la alerta.|  
|Seguridad|Un alerta es pública o privada. A las alertas públicas se puede suscribir c ualquier usuario. A las alertas privadas s olo se pueden suscribir los propietarios correspondientes.|  
|Creado por|Usuario que creó la alerta.|  
|Fecha de creación|Fecha y hora en las que se creó la alerta.|  
|Fecha de última modificación|Fecha y hora en las que se guardó la alerta.|  
|Es propietario|Indica si es propietario de este alerta.|  
  
### <a name="alert-details"></a>Detalles de alerta  
 El **detalles de alerta** área del marco de contenido de administración de alertas proporciona detalles sobre la alerta. Puede usar esta información para determinar si la alerta satisface sus necesidades. También puede modificar la alerta en esta área. En la tabla siguiente se describen los detalles de un alerta.  
  
|Nombre de campo|Contenido|  
|----------------|--------------|  
|Nombre|Nombre de la alerta. El nombre del alerta se utiliza como el asunto de las alertas que se entregan mediante correo electrónico y como el nombre de archivo para las alertas que se entregan como archivo. **Nota:** nombres están limitados a 100 caracteres y no puede contener los caracteres siguientes: ~! @# $% ^&amp;* ();|  
|de mensaje|Texto del mensaje que se entregará con la alerta.|  
|Prioridad|Indica la gravedad del problema que comunica la alerta. Los niveles de prioridad son Superior, Medio e Inferior. Para alertas que se entregan por correo electrónico, este valor determina el tipo de indicador de nivel de importancia en el mensaje de correo electrónico.|  
|Propietarios|Propietario de la alerta. El valor predeterminado para el propietario es el mismo que el del creador de la alerta. En el caso de varios propietarios, éstos se especifican como una lista delimitada por punto y coma.|  
|Área de umbral|Esta área de detalles de alertas solo está presente para las alertas de agregación.|  
|Count<br />(Sólo alerta de agregación)|Lista desplegable de operaciones de comparación.|  
|Valor<br />(Sólo alerta de agregación)|Valor de umbral al que se aplica la comparación. La alerta solo se envía cuando el valor cumple los criterios de comparación. La alerta no se volverá a enviar si se ha restablecido la supervisión debido a que la condición ha dejado de ser verdadera. Por ejemplo, si la alerta se configura para que informe de un importe de pedidos mayor que 1.000 $, la alerta no se volverá a enviar si la cantidad del pedido es menor que 1.000 $. Si el importe del pedido cae por debajo de 1.000 USD y luego vuelve a aumentar, la alerta se volverá a enviar.|  
|Botón Consulta avanzada|Abra el cuadro de diálogo Editor de consultas avanzado. El Editor de consultas avanzado usa expresiones multidimensionales para definir la consulta. Ésta es una característica avanzada y solo la deberían usar los usuarios experimentados. Para obtener más información sobre el lenguaje de consulta de expresiones multidimensionales, vea el capítulo 25 "Multidimensional Expressions" en la referencia de la base de datos del programador de OLE en MSDN en [http://go.microsoft.com/fwlink/?LinkId=58869](http://go.microsoft.com/fwlink/?LinkId=58869).|  
|Restringir búsqueda a la última área|Esta área de detalles de alertas solo está presente para las alertas de agregación. Si la casilla de verificación está activada, sólo se entregará la alerta si el valor de umbral se alcanza durante el período de tiempo determinado. Si la casilla de verificación no está activada, sólo se entregará la alerta cuando el valor de umbral se alcance independientemente del período de tiempo. De forma predeterminada, la casilla se activa cuando se definen dimensiones de tiempo. Si no hay ninguna dimensión de tiempo definida, esta opción no está disponible.|  
|En función de la dimensión<br />(Sólo alerta de agregación)|Determina una dimensión de tiempo a través de la que BAM supervisa para que se alcance el valor de umbral.|  
|Duración<br />(Sólo alerta de agregación)|Un campo de dos partes en el que hay un campo de texto que contiene un valor numérico y una lista desplegable que determina las unidades. El valor de la duración debe ser mayor que cero, e igual o menor que la duración que se estableció en la agregación cuando se creó.|  
|Área de seguridad de alertas|Área de configuración de seguridad.|  
|Permitir que otros vean esta alerta y se suscriban a ella|Una casilla de verificación que cuando está activada permite que otros usuarios con permisos a la vista subyacente puedan ver y suscribir a la alerta. Los propios usuarios se pueden quitar como suscriptores en cualquier momento. Los propietarios de los propietarios de base de datos y de alerta pueden quitar un suscriptor en cualquier momento.|  
  
### <a name="subscriptions"></a>Suscripciones  
 El **suscripciones** área del marco de contenido de administración de alertas permite suscribirse a una alerta. En la tabla siguiente se indica la información que debe proporcionar para suscribirse a una alerta.  
  
|Nombre de campo|Contenido|  
|----------------|--------------|  
|Nombre de usuario|Alias del usuario que se suscribe a la alerta. Este valor se establece automáticamente en el usuario actual.|  
|Transporte|Indica cómo se entrega la alerta. Los métodos de entrega son correo electrónico o archivo.|  
|Dirección|Indica dónde se entregará la alerta. Se trata de una dirección de correo electrónico para el transporte de correo electrónico o una ubicación de archivo definida por el sistema para un método de transporte de archivo. Cuando hay varios suscriptores de correo electrónico a un alerta, un mensaje único de correo electrónico se envía a todos los suscriptores que permite a cualquier suscriptor responder a todos los suscriptores e informarles de la resolución.|  
|Botón Agregar suscriptor|Abre el cuadro de diálogo Agregar suscriptor.|  
  
## <a name="see-also"></a>Vea también  
 [Cómo establecer una alerta](../core/how-to-set-an-alert.md)