---
title: Configurar un lote saliente | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75e6f41a-0e24-47bf-9234-125791c62044
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de6b7ef0a8683374322d4b6f720bc1ebd1ed4b06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234620"
---
# <a name="configuring-an-outgoing-batch"></a>Configurar un lote saliente
Para definir el modo en que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa por lotes los conjuntos de transacciones en un intercambio EDI, debe crear una o varias configuraciones de lotes para un acuerdo. Todos los intercambios que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] asocia a esa acuerdo y que, además, cumplen con los criterios de filtro para un lote, se procesarán por lotes y se lanzarán según los mismos criterios de versión para dicha configuración de lote.  
  
 La configuración de lotes consta de un nombre de lote, identificador de lote, definición del filtro, definición de grupo y criterios de versión y de activación de lotes. Todas las propiedades y opciones relacionadas con lotes están disponibles en la **configuración de lote** página de la ficha de acuerdo unidireccional en el **propiedades del acuerdo de** cuadro de diálogo. Para crear una configuración de lote para un acuerdo, vea [configurar el procesamiento por lotes (X12)](../core/configuring-batching-x12.md).  
  
> [!NOTE]
>  El estándar de documento para el lote se determina a partir de las propias propiedades del acuerdo. Por ejemplo, si el acuerdo es para mensajes X12, el estándar de documento para los lotes será X12.  
  
## <a name="batch-categories"></a>Categorías de lote  
 Use la lista desplegable en la esquina superior derecha de la **configuración de lote** página para determinar qué configuraciones de lote se muestran.  
  
-   **Todos los**: mostrar todas las configuraciones de lote.  
  
-   **Active**: muestra solamente las configuraciones de lote activas.  
  
-   **Inactiva**: muestra solamente las configuraciones de lote inactivas.  
  
## <a name="batch-identification"></a>Identificación de lote  
 La identificación de lote contiene el nombre de lote, la descripción, el identificador de lote y el identificador de la instancia de orquestación de lote.  
  
### <a name="batch-name"></a>Nombre de lote  
 Una configuración de lote se crea basándose en el nombre de lote especificado en **configuración de lote** página de la ficha de acuerdo unidireccional en el **propiedades del acuerdo de** cuadro de diálogo. Varios lotes pueden compartir la misma configuración de seguridad, pero deben tener un nombre de lote único.  
  
### <a name="batch-description"></a>Descripción del lote  
 El cuadro de texto de descripción del lote proporciona una descripción de la configuración del lote.  
  
### <a name="batch-id"></a>Identificador de lote  
 El identificador de lote lo genera automáticamente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cuando se crea una nueva configuración de lote en el **configuración de lote** página. El componente de canalización BatchMarker usa este valor para indicar intercambios entrantes que coincidan con el filtro de lote de una configuración de lote específica. Este valor también se usa como filtro de suscripción de la orquestación de lote asociada con una configuración de lote específica.  
  
### <a name="orchestration-instance-id"></a>Identificador de instancia de orquestación  
 El identificador de instancia de orquestación de la instancia de orquestación de lote que se activa para esta configuración de lote.  
  
## <a name="batch-filter"></a>Filtro por lotes  
 Un lote se crea basándose en la definición de filtro de lote aplicada en el **configuración de lote** página de la ficha de acuerdo unidireccional en el **propiedades del acuerdo de** cuadro de diálogo. En este filtro, se determinarán los conjuntos de transacciones o mensajes que se procesarán por lotes. Puede modificar el valor de este filtro cuando se encuentre activada la instancia de la orquestación de lotes. Cambiar el filtro no influye en los criterios de versión del lote.  
  
> [!NOTE]
>  Si cambia el filtro de lote para un lote activo, los nuevos criterios de filtro necesitarán 15 minutos para activarse, ya que el servidor Biztalk Server almacena esta información en caché. Este intervalo de actualización no se puede modificar.  
>   
>  Para forzar al nuevo filtro a que se active inmediatamente, reinicie el proceso de host de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Los lotes salientes pueden incluir varios grupos, pero solo un grupo por cada tipo de transacción. Un grupo puede contener varios conjuntos de transacciones, pero cada uno debe tener el mismo tipo de transacción.  
  
 Varias configuraciones de lotes pueden compartir el mismo filtro de lote; si un documento coincide con más de un filtro por lotes, se enrutará a todos los lotes coincidentes.  
  
## <a name="group-definition"></a>Definición de grupo  
 Podrá determinar cómo se compondrán los grupos en la salida del lote por medio de la definición de los encabezados de grupo funcional (GS para X12 y UNG para EDIFACT) en las propiedades del acuerdo. Los grupos se encuentran definidos en función de su Identificador de conjunto de transacciones (ST1) para X12 o el Tipo de mensaje (UNH2.1) para EDIFACT, su versión y su espacio de nombres de destino. Por ejemplo, un intercambio puede contener un grupo compuesto por un tipo de mensaje y, por otro lado, un segundo grupo compuesto por otro tipo de mensaje. Para obtener más información acerca de cómo configurar grupos, consulte [configurar propiedades de EDI](../core/configuring-edi-properties.md).  
  
> [!NOTE]
>  El orden de los grupos dentro de un intercambio no está definido.  
  
## <a name="batch-release-criteria"></a>Criterios de versión de lotes  
 Lotes se lanzarán según los criterios establecidos en el **configuración de lote** página de la ficha de acuerdo unidireccional en el **propiedades del acuerdo de** cuadro de diálogo. Los lotes pueden lanzarse de las siguientes formas:  
  
-   En función de una programación, ya sea semanalmente, diariamente o por horas.  
  
-   Cuando un número específico de conjuntos de transacciones se encuentra disponible para un grupo.  
  
-   Cuando un número específico de conjuntos de transacciones se encuentra disponible para un intercambio.  
  
-   Cuando un número específico de caracteres de transacciones se encuentra disponible para un procesamiento por lotes.  
  
-   Cuando una aplicación externa a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ejecuta un desencadenador externo.  
  
 Si selecciona el **enviar señal de lotes vacíos** propiedad en el **programación por lotes** cuadro de diálogo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enviará un mensaje de lotes vacíos cuando el lote está programado para enviarse aunque no hayan ningún mensaje se recibió la orquestación por lotes.  
  
## <a name="batch-activation-criteria"></a>Criterios de activación por lotes  
 Los lotes se lanzarán en función de los criterios de versión de lotes solo cuando se cumpla el criterio de activación de lotes. Para activar una instancia de la orquestación, debe presionar la **iniciar** botón en el **configuración de lote** página de la ficha de acuerdo unidireccional en la **propiedades del acuerdo de**cuadro de diálogo. De este modo se crea una instancia de la orquestación para la configuración de lote. Si el **iniciar** está disponible para hacer clic en botón, una instancia de la orquestación para la configuración de lote no está activada actualmente.  
  
 Después de presionar la **iniciar** botón, los mensajes se recopilarán para un lote únicamente si se cumple lo siguiente:  
  
-   Los mensajes cumplen con los criterios del filtro por lotes.  
  
-   La fecha y hora son posteriores al datetime especificado en el **iniciar** campo.  
  
-   La fecha y hora son anteriores al valor especificado en el **finalizar** campo, o los números de los lotes procesados son menor o igual que el número de repeticiones en el **Finalizar tras (repeticiones)** campo o la  **Sin fecha de finalización** opción está seleccionada. Las tres opciones están disponibles en la **terminación** sección.  
  
 Los criterios de activación se establecen en los **configuración de lote** página de la ficha de acuerdo unidireccional en el **propiedades del acuerdo de** cuadro de diálogo.  
  
 Después de haber presionado el **iniciar** botón para activar una instancia de la orquestación por lotes, los mensajes no se recopilarán para un lote hasta que la hora mencionada para la **iniciar** ha pasado la propiedad.  En el **configuración de lote** página, si **iniciar inmediatamente** no está seleccionada y el **iniciar** fecha y hora se establece en un valor antes de la fecha en que se presiona el **Iniciar** botón, el procesamiento por lotes se iniciará en cuanto la orquestación está activa. Si el datetime de activación se encuentra en un tiempo futuro, el procesamiento por lotes se iniciará en ese momento.  
  
 Puede establecer la **iniciar** que pase a ser una fecha y hora en el futuro. Sin embargo, si hace clic en el **iniciar** botón cuando el **iniciar** datetime está en el futuro, se activará la instancia de orquestación, pero no hay mensajes se recopilarán hasta que se produzca la fecha y hora de inicio. El componente de canalización BatchMarker no promoverá las propiedades apropiadas que se necesitan para enrutar un mensaje a la orquestación de enrutamiento o a la orquestación de lotes hasta que se dé la fecha y hora de inicio. Como resultado, el mensaje no se procesará por lotes. Sin embargo, cualquier puerto u orquestación recogerá los mensajes que les estén suscritos como mensajes individuales. Para obtener más información sobre lo que hace el componente de canalización BatchMarker, vea [ensamblar un intercambio de EDI por lotes](../core/assembling-a-batched-edi-interchange.md).  
  
## <a name="batch-termination-criteria"></a>Criterios de terminación de lotes  
 Los mensajes dejarán de recopilarse para un lote después de la **finalizar** datetime o después del número de repeticiones en el **Finalizar tras (repeticiones)** propiedad. Si no desea que la orquestación por lotes que se desactive, seleccione la **sin fecha de finalización** opción.  
  
> [!NOTE]
>  Si el **Finalizar tras (repeticiones)** se ha seleccionado la propiedad, señales de lotes vacíos contarán para el número de repeticiones requeridas para finalizar el intervalo de activación por lotes. El número de repeticiones también se incrementará si se dan las condiciones que generalmente conducen a una señal de lotes vacíos (la orquestación de lotes no recibe ningún mensaje cuando está programado enviar el lote), pero no se envía ninguna señal de lotes porque la señal no se encuentra configurada.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento por lotes mensajes EDI salientes](../core/batching-outgoing-edi-messages.md)