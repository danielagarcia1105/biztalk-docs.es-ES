---
title: Configuración de la validación (configuración del conjunto de transacciones EDIFACT) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81b30a78-3a4b-4827-9b0a-af9ad3e865a3
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a9ad8f69accd0f479e05e130cc0c28fe874bb86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234004"
---
# <a name="configuring-validation-edifact-transaction-set-settings"></a>Configuración de la validación (configuración del conjunto de transacciones EDIFACT)
La configuración de validación del conjunto de transacciones define el modo en que BizTalk Server valida los conjuntos de transacciones recibidos desde una entidad. Como parte de la configuración de validación, puede especificar qué tipo de validación realizará BizTalk Server en un intercambio entrante.  
  
> [!IMPORTANT]
>  Ninguna propiedad se deshabilita en esta página, incluso si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-ack-processing-and-validation-settings"></a>Para establecer el procesamiento de confirmación y la configuración de validación  
  
1.  Crear un acuerdo de codificación, como se describe en EDIFACT [configuración General de configuración (EDIFACT)](../core/configuring-general-settings-edifact.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración del conjunto de transacciones** sección, haga clic en **validación**.  
  
3.  En la cuadrícula, puede definir diferentes opciones de validación para diferentes conjuntos de transacciones. En el **validación** página, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Default**|Active la casilla para definir una configuración de validación predeterminada.|  
    |**UNH2.1**|Haga clic en la celda vacía de la columna y, en la lista desplegable, seleccione un tipo de transacción.|  
    |**Validación de tipo EDI**|Seleccione **tipo EDI** para habilitar la validación de EDI (elemento de datos) en el receptor del intercambio. Esta validación realiza la validación EDI en los elementos de datos de conjunto de transacciones, tipos de datos de validación, restricciones de longitud, elementos de datos vacíos y separadores finales. Para obtener más información, consulte [validación de tipo EDI (elemento de datos)](../core/edi-type-data-element-validation.md). **Nota:** incluso si esta propiedad no está seleccionada, si está activada en la anotación de esquema se realizará la validación de campos cruzados o segmentos.|  
    |**Validación extendida**|Seleccione esta opción para habilitar la validación extendida (BizTalk XSD) de intercambios recibidos del remitente del intercambio. Esto incluye la validación de longitud de campo, la opcionalidad y el número de repeticiones además de la validación de tipo de datos XSD. Para obtener más información, consulte [validación extendida (BTS-XSD)](../core/extended-bts-xsd-validation.md). **Nota:** puede seleccionar la casilla de verificación solo si **validación de tipo Edi** está seleccionada.|  
    |**Permitir ceros y espacios iniciales y finales**|Seleccione esta opción para especificar que un intercambio EDI recibido de la entidad no se considerará no válido si alguno de sus elementos de datos no cumple su requisito de longitud debido a ceros o espacios iniciales o finales, pero sí lo cumple cuando se eliminan. **Nota:** puede seleccionar la casilla de verificación solo si **validación de tipo Edi** está seleccionada.|  
    |**Directiva de separador final**|-Seleccione **no permite** si no desea permitir delimitadores y separadores finales en un intercambio recibido del remitente de intercambio. Si el intercambio contiene delimitadores y separadores finales, se declarará no válido.<br />-Seleccione **opcional** para aceptar intercambios con o sin delimitadores y separadores finales.<br />-Seleccione **obligatorio** si el intercambio recibido debe contener delimitadores y separadores finales.|  
  
     Puede agregar tantas filas como desee para definir la configuración de validación para intercambios específicos.  
  
     Para eliminar una configuración de validación, seleccione la fila y haga clic en **eliminar**.  
  
    > [!NOTE]
    >  Editar las propiedades de la cuadrícula puede resultar un poco difícil. En su lugar, puede seleccionar la fila que desee editar y, a continuación, edite las mismas propiedades en el **Editar fila seleccionados** sección. La configuración que proporcione aquí se refleja en la fila seleccionada.  
  
4.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar transacción configurar (EDIFACT).](../core/configuring-transaction-set-settings-edifact.md)