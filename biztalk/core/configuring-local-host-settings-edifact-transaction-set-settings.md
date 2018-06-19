---
title: Configuración del Host Local (configuración del conjunto de transacciones EDIFACT) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f7c9cb9-7b4b-41de-a3f3-c0519b18673c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 912af3a047f77f077bf9de58a25802f3c658e6b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234204"
---
# <a name="configuring-local-host-settings-edifact-transaction-set-settings"></a>Configuración de las opciones de host local (configuración del conjunto de transacciones de EDIFACT)
Para procesar un intercambio entrante, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe determinar el esquema que necesita usar en el procesamiento y la validación del intercambio. Esto consiste en determinar el espacio de nombres de destino asociado al esquema y el esquema que se va a utilizar. En esta página de acuerdo de la entidad, especifique las propiedades que se van a usar en la determinación del espacio de nombres de destino. Cómo BizTalk Server determina el esquema se describe en [resolución de acuerdos, detección de esquemas y autorización para los mensajes de EDI recibidos](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).  
  
> [!IMPORTANT]
>  Ninguna propiedad se deshabilita en **entidad A -> B entidad** ficha de acuerdo unidireccional si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación para la entidad A. Sin embargo, se deshabilitan todas las propiedades en la misma página en la **parte B -> parte A** ficha si ha seleccionado la casilla de verificación al crear la entidad A.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="determining-the-target-namespace"></a>Determinar el espacio de nombres de destino  
 En el **personalizar Target Namespace** cuadrícula, puede establecer el espacio de nombres de destino en uno de los espacios de nombres para los esquemas estándares incluidos con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En la cuadrícula, asocie un valor de la **Target Namespace** elemento con los valores de la **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, **UNG2.1**, y **UNG2.2** elementos. Cuando BizTalk recibe un mensaje cuyo **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, **UNG2.1**, y **UNG2.2** elementos coinciden con los de una fila de la cuadrícula, BizTalk usará el espacio de nombres correspondiente para determinar el esquema que va a utilizar para procesar el mensaje. Los valores de los elementos especificados deben ser únicos.  
  
 Si un mensaje no tiene una coincidencia con el **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, **UNG2.1**, y **UNG2.2** elementos en cualquier fila de la cuadrícula, BizTalk Server procesará el mensaje usando el espacio de nombres en la fila para la que el **predeterminado** columna está activada. Esto actúa como el espacio de nombres de destino predeterminado. Si no se identifica ningún espacio de nombres, BizTalk usará el espacio de nombres predeterminado de `http://schemas.microsoft.com/BizTalk/Edi/Edifact/2006`.  
  
> [!NOTE]
>  Si especifica una configuración para algunos de los campos de la cuadrícula y luego la elimina, deberá eliminar la fila completa para evitar errores en la validación de la página.  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>Para configurar el host local para conjuntos de transacciones  
  
1.  Crear un acuerdo de codificación, como se describe en EDIFACT [configuración General de configuración (EDIFACT)](../core/configuring-general-settings-edifact.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración del conjunto de transacciones** sección, haga clic en **configuración de Host Local**.  
  
3.  Como parte de la transacción establece la configuración de la validación, si se establece **directiva de separador final** a **opcional** o **obligatorio**, puede seleccionar **crear vacío Etiquetas XML para los separadores finales** para que el remitente del intercambio incluya etiquetas XML vacías para separadores finales.  
  
4.  Seleccione **usar punto (.) como separador decimal** para habilitar el servidor BizTalk Server incluyen un punto (.) en el mensaje XML creado a partir de un intercambio que contiene un número decimal.  
  
5.  En el **personalizar Target Namespace** sección, realice lo siguiente:  
  
    1.  Seleccione el **predeterminado** casilla de verificación de la fila que contiene el espacio de nombres de destino predeterminado que desee definir.  
  
    2.  En el **UNH2.1** columna, especifique el tipo de mensaje. (seis caracteres como máximo).  
  
    3.  En el **UNH2.2** columna, especifique el número de versión de mensaje. (un carácter como mínimo; tres caracteres como máximo).  
  
    4.  En el **UNH2.3** columna, especifique el número de versión de mensaje. (un carácter como mínimo; tres caracteres como máximo).  
  
    5.  En el **UNH2.5** columna, especifique el código asignado. (seis caracteres como máximo. Debe ser alfanumérico.  
  
    6.  En el **UNG2.1** columna, escriba un valor alfanumérico para la identificación del remitente de aplicación con un mínimo de 1 carácter y un máximo de 35 caracteres. Este campo es obligatorio.  
  
    7.  En el **UNG2.2** columna, escriba un valor alfanumérico para el calificador de código de remitente de aplicación con un carácter como mínimo y un máximo de cuatro caracteres. Este campo es opcional.  
  
    8.  En el **Target Namespace** columna, seleccione en la lista desplegable o escriba el espacio de nombres de destino que se usará para un intercambio cuando no se encuentra ninguna coincidencia entre los elementos de datos en cualquier fila de la cuadrícula y los campos en el intercambio.  
  
        > [!NOTE]
        >  Estos serán los valores que BizTalk Server comparará con los valores asociados al intercambio que ha recibido.  
  
    9. Repita estos pasos para cualquier otro espacio de nombres de destino que se vaya a usar.  
  
    10. Para quitar un espacio de nombres de destino de la lista, seleccione la fila y haga clic en **eliminar**.  
  
6.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar transacción configurar (EDIFACT).](../core/configuring-transaction-set-settings-edifact.md)