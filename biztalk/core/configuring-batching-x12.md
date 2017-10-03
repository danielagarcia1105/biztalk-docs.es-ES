---
title: Configurar el procesamiento por lotes (X12) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f4f9e7b-262d-488e-9a04-088aad289d70
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7912aad3610b7c05ddc0db37f6c7989be3bc04a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-batching-x12"></a>Configuración del procesamiento por lotes (X12)
Los lotes definen cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera y envía lotes EDI a la entidad.  
  
> [!NOTE]
>  La configuración descrita aquí también se aplica a los intercambios HIPAA.  
  
> [!IMPORTANT]
>  Todas las propiedades se deshabilitan en esta página, incluso si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato. El **nuevo lote** botón está deshabilitado en esta página.  
>   
>  Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad. Por ejemplo, si crea dos entidades, entidad A y entidad B y para la entidad A ha desactivado la casilla de verificación, el **nuevo lote** botón está deshabilitado en el **entidad A -> B entidad** ficha de acuerdo unidireccional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-batching-settings"></a>Para configurar el procesamiento por lotes  
  
1.  Crear un acuerdo de codificación, como se describe en X12 [General configuración (X12)](../core/configuring-general-settings-x12.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **configuración de procesamiento por lotes**.  
  
3.  Desde el **configuración de lote** página haga clic en **nuevo lote** para crear una nueva configuración de lote. A **Batch1** pestaña se agrega.  
  
4.  En el **identificación** sección de la ficha realice los pasos siguientes:  
  
    1.  Escriba el **lote** nombre. Este valor se usa como identificador de la pestaña para esta configuración de lote.  
  
    2.  Escriba una descripción de esta configuración por lotes en **por lotes descripción**.  
  
    3.  **Identificador de lote** es un cuadro de texto de solo lectura que muestra un identificador de lote único tras aplicar la configuración para el lote.  
  
    4.  **Id. de instancia de orquestación** es un cuadro de texto de solo lectura que muestra el identificador de instancia de orquestación por lotes que está asociado el lote. Se muestra un identificador de instancia de orquestación una vez que se ha iniciado un lote.  
  
5.  En el **filtro** sección de la ficha realice los pasos siguientes:  
  
    1.  Haga clic en **filtro**.  
  
    2.  En el **filtro por lotes** diálogo cuadro, escriba la propiedad, operador y valores para generar el filtro de suscripción para la orquestación por lotes. Estas cláusulas de filtro determinan qué conjuntos de transacciones enrutará la orquestación de enrutamiento al cuadro de mensajes para el procesamiento por lotes.  
  
        > [!NOTE]
        >  Para especificar que se van a procesar por lotes todos los mensajes con destino a un grupo, establezca en el nombre de la entidad la propiedad de la entidad del filtro por lotes.  
  
        > [!NOTE]
        >  Para obtener más información acerca del procesamiento por lotes, vea [ensamblar un intercambio de EDI por lotes](../core/assembling-a-batched-edi-interchange.md).  
  
    3.  Para eliminar una fila, seleccione la fila y haga clic en **eliminar**.  
  
    4.  Para mover una fila hacia arriba o hacia abajo, haga clic en el **Subir** o **mover hacia abajo** botones.  
  
6.  En el **versión** sección de la ficha realice los pasos siguientes:  
  
    1.  Seleccione **programación** para crear y enviar un lote según una programación predeterminada. Para definir la programación, haga clic en **programador** y, a continuación, haga lo siguiente:  
  
        > [!NOTE]
        >  Los eventos especiales pueden afectar a una programación por lotes. Un ejemplo de ello es el establecimiento del horario de verano. Si se ha programado un lote para que se ejecute cada hora menos de una hora antes de que se cambie al horario de verano, el lote no se creará y enviará después de que los relojes se adelanten una hora. Es posible compensar eventos especiales que son el resultado de la omisión de un lote, haga clic en el **iniciar** situado en la **lotes** página para iniciar la orquestación por lotes manualmente. Es posible que también sea necesario detener un lote duplicado.  
  
        -   Para enviar un lote cada hora, seleccione **cada hora**. En la lista desplegable de **primer lanzamiento en**, seleccione una fecha para la primera versión del lote y, a continuación, especifique la hora. Para **versión posterior cada**, seleccione en la lista desplegable si el punto está en **horas** o **minutos**y, a continuación, escriba el número de horas o minutos que Separe cada lote.  
  
        -   Para enviar un lote a diario, seleccione **diario**. En la lista desplegable de **primer lanzamiento en**, seleccione una fecha para la primera versión del lote y, a continuación, especifique la hora. Para **versión posterior cada**, escriba el número de días que separarán cada lote.  
  
        -   Para enviar un lote cada semana, seleccione **semanal**. En la lista desplegable de **primer lanzamiento en**, seleccione una fecha para la primera versión del lote y, a continuación, especifique la hora. Para **versión posterior cada**, escriba el número de semanas entre la semana de la primera versión y la semana de las versiones posteriores. A continuación, seleccione los días de la semana en que se realizará la versión del lote.  
  
            > [!NOTE]
            >  La primera versión se realizará en la fecha y defina el **primer lanzamiento en** campo, incluso si ese día de la semana no se ha seleccionado en el cuadro de diálogo.  
  
            > [!NOTE]
            >  Si ha seleccionado uno o varios días de la semana en el cuadro de diálogo, se realizará un lanzamiento cada día seleccionado de la primera semana posterior al primer lanzamiento. Por ejemplo, si ha seleccionado el lunes y el viernes, y la primera versión fue el miércoles, se realizará una versión el viernes de la primera semana. Versiones subsiguientes tendrán lugar  *n*  semanas después de la primera semana con  *n*  determinado por el valor de la **versión posterior cada** campo. La versión se producirá todos los días de la semana seleccionados en el cuadro de diálogo.  
  
        -   Seleccione **enviar señal de lotes vacíos** para enviar una señal de lotes vacíos si no se ha recibido ningún mensaje de la orquestación por lotes cuando esté programado que se envía el lote.  
  
    2.  Seleccione **establece el número máximo de transacciones** para crear y enviar un lote cuando se enrute un número determinado de mensajes o conjuntos de transacciones en el cuadro de mensajes para procesar por lotes. Seleccione la parte del mensaje para contar la transacción se establece en (ya sea **grupo** o **intercambio**) y, a continuación, escriba el número máximo de conjuntos de transacciones deben estar en el grupo por lotes o intercambio.  
  
         Por ejemplo, seleccione si desea agrupar dos intercambios en un proceso por lotes **intercambio** en la lista desplegable y escriba `2` en el cuadro de texto.  
  
    3.  Seleccione **número máximo de caracteres en un intercambio** para crear y enviar un lote cuando un número específico de caracteres está disponible para el procesamiento por lotes. Especifique el número máximo de caracteres en el intercambio o grupo por lotes.  
  
         La orquestación de procesamiento por lotes acumulará los elementos de procesamiento por lotes hasta que el recuento de caracteres en esos elementos (menos el recuento del sobre) exceda el recuento máximo. Entonces, se agruparán en un lote todos los elementos excepto el último (que ha causado que se exceda el recuento máximo).  
  
        > [!NOTE]
        >  Para el número máximo de caracteres, especifique un número lo suficientemente grande para poder generar lotes significativos. Este número debería ser, como mínimo, mayor que el número total de caracteres de los encabezados de lotes y el número máximo de caracteres de un mensaje. Un número demasiado pequeño podría dar lugar a lotes vacíos.  
  
    4.  Seleccione **desencadenador de versión externo** para crear y, a continuación, enviar un lote cuando una aplicación externa a BizTalk Server ejecuta un desencadenador externo. Para obtener más información acerca de cómo configurar este mecanismo, vea [implementar un mecanismo de liberación de lote externo](../core/implementing-an-external-batch-release-mechanism.md).  
  
        > [!NOTE]
        >  El **invalidar** botón y **intervalo de activación** controles siguen siendo válidos si la **versión externo** se ha seleccionado la propiedad de desencadenador.  
  
7.  En el **activación** sección de la ficha realice los pasos siguientes:  
  
    1.  Seleccione **iniciar inmediatamente** para que el procesamiento por lotes, orquestación comenzar inmediatamente los mensajes por lotes.  
  
         Para iniciar la orquestación por lotes en una fecha específica, desactive la **iniciar inmediatamente** cuadro y seleccione una fecha y hora para activar la orquestación por lotes.  
  
8.  En el **terminación** sección de la ficha realice los pasos siguientes:  
  
    1.  Mantener **sin fecha de finalización** seleccionada si no desea especificar una fecha de finalización de la orquestación por lotes que se desactive.  
  
    2.  Seleccione **Finalizar tras (repeticiones)** para especificar que la orquestación por lotes se desactivará después de haber generado un determinado número de lotes. Especifique el número deseado en el cuadro de texto.  
  
    3.  Seleccione **finalizar** para especificar una fecha de finalización que se desactivará la orquestación por lotes. A partir de esta hora ya no se recopilarán mensajes para el procesamiento por lotes. Seleccione una fecha de finalización del calendario o modifique la hora o la fecha directamente en el cuadro de texto.  
  
9. Haga clic en **aplicar** para aplicar la configuración de lote proporcionado en los pasos anteriores. Tras hacer clic en **aplicar**, un lote identificador se crea y se muestra en el **Id. de lote** campo de texto en el **identificación** sección.  
  
    > [!NOTE]
    >  Un mensaje **no se ha activado el procesamiento por lotes** se mostrarán en el **iniciar** botón.  
  
10. Haga clic en **iniciar** para activar una orquestación de procesamiento por lotes manualmente.  
  
    > [!NOTE]
    >  Para asegurarse de que la orquestación por lotes se activará inmediatamente al hacer clic en el **iniciar** botón, actualice el intervalo de sondeo de ubicación de recepción del adaptador SQL en el BatchControlMessageReccvLoc. Para obtener más información, consulte [tutorial (X12): enviar intercambios de EDI por lotes](../core/walkthrough-x12-sending-batched-edi-interchanges.md).  
  
    > [!NOTE]
    >  Tras hacer clic en **iniciar**, haga clic en **actualizar**. Puede que se tarde un tiempo en asociar el lote con la instancia de orquestación. Si hace clic en **actualizar** antes de que el lote está asociado a la orquestación, verá el mensaje **procesamiento por lotes está activado, todavía no crean instancia de orquestación por lotes**. Haga clic en **actualizar** nuevo, para ver el Id. de instancia de orquestación asociada en el **Id. de instancia de orquestación** cuadro de texto. El mensaje **procesamiento por lotes está activado** se muestra bajo la **iniciar** botón.  
  
11. Haga clic en **invalidar** para forzar la orquestación por lotes para enviar un lote, si no se cumplen los criterios de lanzamiento. Mediante esta opción se invalidan los criterios de procesamiento por lotes existentes, con lo que se creará un lote con los elementos existentes y se enviará inmediatamente a continuación. Después, la orquestación de procesamiento por lotes reanuda el procesamiento por lotes según la configuración establecida.  
  
12. Haga clic en **detener** para finalizar una orquestación de procesamiento por lotes activa sin enviar un lote y desactivar manualmente la orquestación de procesamiento por lotes.  
  
13. Haga clic en **actualizar** para actualizar el estado de la orquestación por lotes.  
  
    > [!NOTE]
    >  Puede usar la lista desplegable en la parte superior de **la configuración de lote** página para filtrar las fichas de configuración de lote mostradas seleccionando **todos los** (para ver las fichas para todos los lotes), **activo** (para ver las fichas de los lotes activos), o **inactivo** (para ver las fichas para lotes inactivos).  
  
    > [!NOTE]
    >  Si se modifican los valores de configuración mientras la orquestación está procesando un lote, los nuevos valores no se aplicarán a ese lote. Esto puede dar como resultado errores de validación en la canalización de envío.  
  
    > [!NOTE]
    >  Para acelerar la activación de la entidad de orquestación de procesamiento por lotes en un servidor de desarrollo, puede reducir el intervalo de sondeo para la ubicación de recepción del adaptador SQL de procesamiento por lotes (BatchControlMessageRecvLoc) en ese servidor. Se recomienda establecer en 30 segundos el intervalo de sondeo para un servidor de desarrollo.  
  
14. Haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de intercambio (X12)](../core/configuring-interchange-settings-x12.md)   
 [Configurar un lote saliente](../core/configuring-an-outgoing-batch.md)   
 [Ensamblar un intercambio EDI por lotes](../core/assembling-a-batched-edi-interchange.md)   
 [Implementar un mecanismo de liberación de lote externo](../core/implementing-an-external-batch-release-mechanism.md)