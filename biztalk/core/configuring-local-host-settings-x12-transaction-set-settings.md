---
title: "Configuración del Host Local (configuración de conjunto de transacciones de X12) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e31b41c3-49fc-46ef-ab69-889e30dfc58e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fcc099535e6a7b96c5c4bbdd29112da46af3522
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-local-host-settings-x12-transaction-set-settings"></a>Configuración de las opciones de host local (configuración del conjunto de transacciones de X12)
Para procesar un intercambio entrante, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe determinar el esquema que necesita usar en el procesamiento y la validación del intercambio. Esto consiste en determinar el espacio de nombres de destino asociado al esquema y el esquema que se va a utilizar. En esta página de acuerdo de la entidad, especifique las propiedades que se van a usar en la determinación del espacio de nombres de destino. Cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determina el esquema se describe en [resolución de acuerdos, detección de esquemas y autorización para los mensajes de EDI recibidos](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).  
  
> [!NOTE]
>  Este tema se aplica también a valores de configuración relacionados con HIPAA.  
  
> [!IMPORTANT]
>  Ninguna propiedad se deshabilita en **entidad A -> B entidad** ficha de acuerdo unidireccional si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación para la entidad A. Sin embargo, se deshabilitan todas las propiedades en la misma página en la **parte B -> parte A** ficha si ha seleccionado la casilla de verificación al crear la entidad A.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="determining-the-target-namespace"></a>Determinar el espacio de nombres de destino  
 En el **espacio de nombres de destino personalizar** cuadrícula, puede establecer los espacios de nombres de destino en uno de los espacios de nombres para los esquemas estándares suministrados con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En la cuadrícula, asocie un valor de la **Target Namespace** elemento con los valores del remitente de aplicación (**GS2**) y código de identificador de conjunto de transacciones (**ST1**). Cuando BizTalk recibe un mensaje cuyo **GS2** y **ST1** elementos de datos coinciden con los de una fila de la cuadrícula, BizTalk usará el espacio de nombres correspondiente para procesar el mensaje. Los valores de los elementos especificados deben ser únicos.  
  
 Si un mensaje no tiene una coincidencia con el **GS2** y **ST1** elementos de datos en cualquier fila de la cuadrícula, BizTalk Server procesará el mensaje usando el espacio de nombres en la fila para la que el **predeterminado** columna está activada. Esto actúa como el espacio de nombres de destino predeterminado. Si no se identifica ningún espacio de nombres, BizTalk Server usará el espacio de nombres predeterminado de `http://schemas.microsoft.com/BizTalk/Edi/EDIFACT/2006`.  
  
> [!NOTE]
>  Si especifica una configuración para algunos de los campos de la cuadrícula y luego la elimina, deberá eliminar la fila completa para evitar errores en la validación de la página.  
  
> [!NOTE]
>  Para obtener un ejemplo de uso de esta cuadrícula, ejecute el tutorial de programadores de la interfaz EDI, en concreto la configuración de una entidad de la que se va a recibir un intercambio. Para obtener más información, consulte [paso 4: configurar una entidad y perfil de negocio para el socio comercial](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md).  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>Para configurar el host local para conjuntos de transacciones  
  
1.  Crear un acuerdo de codificación, como se describe en X12 [General configuración (X12)](../core/configuring-general-settings-x12.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración del conjunto de transacciones** sección, haga clic en **configuración de Host Local**.  
  
3.  Seleccione **convertir formato decimal implícito Nn a valor numérico 10 base** para convertir un número EDI especificado con el formato Nn en un valor numérico de base 10 en el XML intermedio en BizTalk Server.  
  
    > [!NOTE]
    >  Después de esta conversión, puede haber errores en la validación de la longitud del XML intermedio. Ello se debe a que el número en formato numérico de base 10 incluye un decimal, lo que conlleva que su longitud sea superior en uno al número en formato Nn. Puede resolver este problema, agregue un valor de **1** en el valor de longitud mínima o máxima.  
  
4.  Como parte de la transacción establece la configuración de la validación, si se establece **directiva de separador final** a **opcional** o **obligatorio**, puede seleccionar **crear vacío Etiquetas XML para los separadores finales** para que el remitente del intercambio incluya etiquetas XML vacías para separadores finales.  
  
5.  En el **personalizar Target Namespace** sección, realice lo siguiente:  
  
    1.  Seleccione el **predeterminado** casilla de verificación de la fila que contiene el espacio de nombres de destino predeterminado que desee definir.  
  
    2.  En el **para ST1** código identificador del conjunto de columnas, seleccione un valor para la transacción en la lista desplegable.  
  
    3.  En el **GS2** columna, escriba un valor alfanumérico para el remitente de aplicación con un mínimo de dos caracteres y un máximo de 15 caracteres. Este campo es obligatorio.  
  
    4.  En el **Target Namespace** columna, seleccione en la lista desplegable o escriba el espacio de nombres de destino que se usará para un intercambio cuando no se encuentra ninguna coincidencia entre los elementos de datos en cualquier fila de la cuadrícula y los campos en el intercambio.  
  
        > [!NOTE]
        >  Estos serán los valores que BizTalk Server comparará con los valores asociados al intercambio que ha recibido.  
  
    5.  Repita estos pasos para cualquier otro espacio de nombres de destino que se vaya a usar.  
  
    6.  Para quitar un espacio de nombres de destino de la lista, seleccione la fila y haga clic en **eliminar**.  
  
6.  Haga clic en **aplicar** para aceptar los cambios o haga clic en **Aceptar** para introducir y validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar transacción configurar (X12)](../core/configuring-transaction-set-settings-x12.md)