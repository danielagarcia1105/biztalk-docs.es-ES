---
title: Configuración de sobres (configuración de conjunto de transacciones de X12) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9313a7b9-72fa-4071-8c65-007371643179
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 519062fa4647cdc2c7c39dda19373ff888eaf601
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234340"
---
# <a name="configuring-envelopes-x12-transaction-set-settings"></a>Configuración de sobres (configuración del conjunto de transacciones X12)
En el **sobres** página de la **configuración del conjunto de transacciones** sección, defina cómo BizTalk Server genera los segmentos GS y ST para un intercambio codificado en X12 que envía a la entidad. El segmento GS identifica y especifica un grupo funcional para un intercambio con codificación X12. El segmento ST es el encabezado de mensaje para el intercambio con codificación X12.  
  
 En esta página, asociar valores de la **GS1**, **GS2**, **GS3**, **GS4**, **GS5**, **GS7**, y **GS8** elementos de datos con valores de la **tipo de transacción**, **versión**, y **destino espacio de nombres** elementos de datos. Cuando BizTalk determina que un mensaje XML de BizTalk contiene los valores establecidos para la **tipo de transacción**, **versión**, y **espacio de nombres de destino** elementos en una fila de la cuadrícula BizTalk rellenará el **GS1**, **GS2**, **GS3**, **GS4**, **GS5**, **GS7**, y **GS8** elementos de datos en la envolvente de la salida del intercambio con los valores de la misma fila de la cuadrícula. Los valores de la **tipo de transacción**, **versión**, y **espacio de nombres de destino** elementos deben ser únicos.  
  
> [!NOTE]
>  Si especifica una configuración para algunos de los campos de la cuadrícula y luego la elimina, deberá eliminar la fila completa para evitar errores en la validación de la página.  
  
> [!NOTE]
>  Este tema se aplica también a valores de configuración relacionados con HIPAA.  
  
> [!IMPORTANT]
>  Todas las propiedades están deshabilitadas en **entidad A -> B entidad** ficha de acuerdo unidireccional si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** comprobar cuadro de entidad A. Sin embargo, todas las propiedades están habilitadas en la misma página en la **parte B -> parte A** ficha si ha seleccionado la casilla de verificación al crear la entidad A.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-define-the-gs-and-st-segments"></a>Para definir los segmentos GS y ST  
  
1.  Crear un acuerdo de codificación, como se describe en X12 [General configuración (X12)](../core/configuring-general-settings-x12.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración del conjunto de transacciones** sección, haga clic en **sobres**.  
  
3.  En una fila de la cuadrícula, especifique lo siguiente:  
  
    -   Para el **tipo de transacción** , a continuación, seleccione un valor para el conjunto de transacciones código de identificador de la lista desplegable.  
  
    -   Para **versión**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de 12 caracteres.  
  
    -   Para **espacio de nombres de destino** elementos, seleccione un valor de la lista desplegable o escriba un espacio de nombres.  
  
        > [!NOTE]
        >  Estos serán los valores que BizTalk Server compare con los valores asociados con el intercambio que se crea.  
  
4.  En la misma fila de la cuadrícula, especifique lo siguiente:  
  
    -   Para **GS1**, seleccione un valor para el código funcional en la lista desplegable. Se trata de un campo opcional.  
  
    -   Para **GS2**, escriba un valor alfanumérico para el remitente de aplicación con un mínimo de dos caracteres y un máximo de 15 caracteres. Este campo es obligatorio.  
  
    -   Para **GS3**, escriba un valor alfanumérico para el receptor de aplicación con un mínimo de dos caracteres y un máximo de 15 caracteres. Este campo es obligatorio.  
  
    -   Para **GS4**, seleccione **SSAAMMDD** o **AAMMDD**. Este campo es opcional  
  
    -   Para **GS5**, seleccione **HHMM**, **HHMMSS**, o **HHMMSSdd**. Este campo es opcional  
  
    -   Para **GS7**, seleccione un valor para la Agencia responsable de la lista desplegable. Se trata de un campo opcional.  
  
    -   Para **GS8**, escriba un valor alfanumérico para el documento identificado con un carácter como mínimo y un máximo de 12 caracteres. Se trata de un campo opcional.  
  
        > [!NOTE]
        >  Estos serán los valores que BizTalk Server especificará en los campos GS del intercambio que está construyendo si el **tipo de transacción**, **versión**, y **el espacio de nombres de destino**elementos en la misma fila son una coincidencia para los que estén asociados con el intercambio.  
  
5.  Repita los pasos 3 y 4 para especificar las filas adicionales en la cuadrícula.  
  
6.  Para una fila en la cuadrícula, haga clic en **predeterminado** para establecerla como la fila predeterminada.  
  
    > [!NOTE]
    >  Si un mensaje no tiene una coincidencia con el **tipo de transacción**, **versión**, y **espacio de nombres de destino** elementos en cualquier fila, BizTalk Server rellenará el mensaje con los valores de la **GS1**, **GS2**, **GS3**, **GS5**, **GS7**y **GS8** elementos en la fila predeterminada. Estos valores se utilizarán incluso si el mensaje no tiene una coincidencia con el **tipo de transacción**, **versión**, y **espacio de nombres de destino** elementos de la fila predeterminada.  
  
    > [!NOTE]
    >  Si no tiene valor predeterminado está seleccionados, los documentos entrantes que no coinciden con la **tipo de transacción**, **versión**, y **espacio de nombres de destino** se suspenderán los elementos de todas las filas .  
  
7.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar transacción configurar (X12)](../core/configuring-transaction-set-settings-x12.md)