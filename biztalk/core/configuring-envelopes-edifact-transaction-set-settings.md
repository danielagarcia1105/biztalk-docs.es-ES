---
title: "Configuración de sobres (configuración del conjunto de transacciones EDIFACT) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec140def-6155-4b8a-8489-6e0a530bd697
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a1d910f52d9ea90ae0c486356a7ecb3b01bf07a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-envelopes-edifact-transaction-set-settings"></a>Configuración de sobres (configuración del conjunto de transacciones EDIFACT)
En el **sobres** página de la **configuración del conjunto de transacciones** sección, defina cómo BizTalk Server genera los segmentos UNG y UNH para un intercambio con codificación EDIFACT que envía a la entidad.  
  
 El segmento UNG es el encabezado que identifica y especifica un grupo funcional de un intercambio codificado en EDIFACT. Contiene información acerca de la fecha y la hora en la que el grupo funcional se preparó, junto con el tipo y la versión del documento en el grupo funcional.  
  
 El segmento UNH es el segmento del encabezado del mensaje de un intercambio codificado en EDIFACT. Proporciona información acerca del tipo de mensaje, y de la agencia responsable de mantener la publicación del tipo de mensaje. Este segmento indica el inicio de un documento dentro de un intercambio e indica el tipo de documento que sigue.  
  
 En el **encabezado de grupo funcional (UNG)** sección, asociar **UNG** valores con **UNH** valores y un espacio de nombres. Cuando BizTalk Server determina que un mensaje XML de BizTalk contiene los valores establecidos para la **UNH** elementos y **espacio de nombres de destino** en una fila de la cuadrícula, BizTalk Server rellenará el **UNG** elementos de datos con los valores de la misma fila de la cuadrícula. Los valores de la **UNH** elementos y **espacio de nombres de destino** deben ser únicos.  
  
 Si un mensaje no tiene una coincidencia con el **UNH** elementos y **espacio de nombres de destino** en ninguna fila, BizTalk Server rellenará el mensaje con los valores de la **UNG** elementos de la fila predeterminada. Estos valores se utilizarán incluso si el mensaje no tiene una coincidencia con el **UNH** elementos y **espacio de nombres de destino** de la fila predeterminada.  
  
 Cuando el motor de BizTalk determina que un mensaje XML de BizTalk contiene los valores establecidos para los elementos UNH y el espacio de nombres de destino, el motor completará los elementos UNG en el mensaje con los valores establecidos para ellos en la cuadrícula, siempre la **crear agrupación Segmentos** casilla de verificación está activada.  
  
> [!NOTE]
>  En el **encabezado de grupo funcional (UNG)** sección, si especifica una configuración para cualquiera de los campos en la cuadrícula y, a continuación, lo elimina, tendrá que eliminar toda la fila o la página se considerará no válido.  
  
> [!IMPORTANT]
>  Todas las propiedades están deshabilitadas en **entidad A -> B entidad** ficha de acuerdo unidireccional si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** comprobar cuadro de entidad A. Sin embargo, todas las propiedades están habilitadas en la misma página en la **parte B -> parte A** ficha si ha seleccionado la casilla de verificación al crear la entidad A.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-define-the-ung-and-unh-segments"></a>Para definir los segmentos UNG y UNH  
  
1.  Crear un acuerdo de codificación, como se describe en EDIFACT [configuración General de configuración (EDIFACT)](../core/configuring-general-settings-edifact.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración del conjunto de transacciones** sección, haga clic en **sobres**.  
  
3.  En una fila de la cuadrícula, escriba los valores siguientes:  
  
    -   En el **para mensaje escriba UNH2.1** columna, escriba un tipo de conjunto de transacciones. (Máximo seis caracteres.)  
  
    -   En el **UNH2.2** columna, escriba el número de versión de mensaje. (Un carácter como mínimo; tres caracteres como máximo).  
  
    -   En el **UNH2.3** columna, escriba el número de versión de mensaje. (Un carácter como mínimo; tres caracteres como máximo).  
  
    -   En el **UNH2.5** columna, escriba el código asignado. (Máximo seis caracteres. Debe ser alfanumérico.  
  
    -   En el **espacio de nombres de destino** columna, seleccione el espacio de nombres de destino del esquema. Este campo es obligatorio.  
  
        > [!NOTE]
        >  Estos serán los valores que BizTalk Server compare con los valores asociados con el intercambio que se crea.  
  
4.  En la misma fila de la cuadrícula, escriba uno de los valores siguientes:  
  
    -   Para el **UNG1** (identificación de grupo funcional), escriba un valor alfanumérico con un carácter como mínimo y un máximo de seis caracteres. Este campo es obligatorio.  
  
    -   Para **UNG2.1** (identificación de remitente de aplicación), escriba un valor alfanumérico con un carácter como mínimo y un máximo de 35 caracteres. Este campo es obligatorio.  
  
    -   Para **UNG2.2** (calificador de código de remitente de aplicación), escriba un valor alfanumérico con un máximo de cuatro caracteres. Se trata de un campo opcional.  
  
    -   Para **UNG3.1** (aplicación identificación del destinatario), escriba un valor alfanumérico con un carácter como mínimo y un máximo de 35 caracteres. Este campo es obligatorio.  
  
    -   Para **UNG3.2** (calificador de código del destinatario de aplicación), escriba un valor alfanumérico con un máximo de cuatro caracteres. Se trata de un campo opcional.  
  
    -   Para **UNG6** (Agencia de control), escriba un valor alfanumérico con un mínimo y un máximo de dos. Este campo es obligatorio.  
  
    -   Para **UNG7.1** (número de versión de tipo de mensaje), escriba un valor alfanumérico con un carácter como mínimo y un máximo de tres caracteres. Este campo es obligatorio.  
  
    -   Para **UNG7.2** (número de versión de tipo de mensaje), escriba un valor alfanumérico con un carácter como mínimo y un máximo de tres caracteres. Este campo es obligatorio.  
  
    -   Para **UNG7.3** (asignado a la asociación código), escriba un valor alfanumérico con un mínimo de 1 carácter y un máximo de 6 caracteres. Este campo es obligatorio.  
  
    -   Para **UNG8** (contraseña de aplicación), escriba un valor alfanumérico con un carácter como mínimo y un máximo de 14 caracteres. Este campo es obligatorio.  
  
        > [!NOTE]
        >  Estos serán los valores que BizTalk Server especificará en los campos UNG del intercambio que está construyendo si el **para mensaje escriba UNH2.1**, **UNH2.2**, **UNH2.3**,  **UNH2.5**, y **espacio de nombres de destino** elementos en la misma fila son una coincidencia para los que estén asociados con el intercambio.  
  
5.  Repita los pasos 4 y 5 para especificar las filas adicionales en la cuadrícula.  
  
6.  Para una fila en la cuadrícula, haga clic en **predeterminado** para establecerla como la fila predeterminada.  
  
    > [!NOTE]
    >  Si un mensaje no tiene una coincidencia con el **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, y **deespaciodenombresdedestino** elementos en cualquier fila, BizTalk Server rellenará el mensaje con los valores de la **UNG1**, **UNG2.1**, **UNG2.2**,  **UNG3.1**, **UNG3.2**, **UNG6**, **UNG7.1**, **UNG7.2**, **UNG7.3**, y **UNG8** elementos en la fila predeterminada. Estos valores se utilizarán incluso si el mensaje no tiene una coincidencia con el **para mensaje escriba UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, y **espacio de nombres de destino** elementos de la fila predeterminada.  
  
    > [!NOTE]
    >  Si no se selecciona ninguna fila predeterminada, y el mensaje no tiene una coincidencia para la **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**y **Espacio de nombres de destino** elementos en una fila, BizTalk suspenderá el mensaje.  
  
7.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar transacción configurar (EDIFACT).](../core/configuring-transaction-set-settings-edifact.md)