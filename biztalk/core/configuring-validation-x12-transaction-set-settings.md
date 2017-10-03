---
title: "Configuración de la validación (configuración de conjunto de transacciones de X12) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0245be7f-d212-43b1-bfef-cbcbd851b5c0
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 880a8d1e31cbb10f570dcf5e7422a1e61b5cc8d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-validation-x12-transaction-set-settings"></a>Configuración de la validación (configuración del conjunto de transacciones X12)
La configuración de validación del conjunto de transacciones define el modo en que BizTalk Server valida los conjuntos de transacciones recibidos desde una entidad. Como parte de la configuración de validación, puede especificar qué tipo de validación realizará BizTalk Server en un intercambio entrante.  
  
> [!NOTE]
>  Este tema se aplica también a la configuración de la validación de HIPAA.  
  
> [!IMPORTANT]
>  Ninguna propiedad se deshabilita en esta página, incluso si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-validation-settings"></a>Procedimiento para configurar la configuración de validación  
  
1.  Crear un acuerdo de codificación, como se describe en X12 [General configuración (X12)](../core/configuring-general-settings-x12.md). Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración del conjunto de transacciones** sección, haga clic en **validación**.  
  
3.  En la cuadrícula, puede definir diferentes opciones de validación para diferentes conjuntos de transacciones. En el **validación** página, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Default**|Active la casilla para definir una configuración de validación predeterminada.|  
    |**Tipo de transacción**|Haga clic en la celda vacía de la columna y, en la lista desplegable, seleccione un tipo de transacción.|  
    |**Validación de tipo EDI**|Seleccione esta opción para habilitar la validación EDI (elemento de datos) en el receptor de intercambio. Esta validación realiza la validación EDI en los elementos de datos de conjunto de transacciones, tipos de datos de validación, restricciones de longitud, elementos de datos vacíos y separadores finales. Para obtener más información, consulte [validación de tipo EDI (elemento de datos)](../core/edi-type-data-element-validation.md). **Nota:** incluso si esta propiedad no está seleccionada, si está activada en la anotación de esquema se realizará la validación de campos cruzados o segmentos.|  
    |**Validación extendida**|Seleccione esta opción para habilitar la validación extendida (BizTalk XSD) de intercambios recibidos del remitente del intercambio. Esto incluye la validación de longitud de campo, la opcionalidad y el número de repeticiones además de la validación de tipo de datos XSD. Para obtener más información, consulte [validación extendida (BTS-XSD)](../core/extended-bts-xsd-validation.md). **Nota:** puede seleccionar la casilla de verificación solo si **validación de tipo Edi** está seleccionada.|  
    |**Permitir ceros y espacios iniciales y finales**|Seleccione esta opción para especificar que un intercambio EDI recibido de la entidad no se considerará no válido si alguno de sus elementos de datos no cumple su requisito de longitud debido a ceros o espacios iniciales o finales, pero sí lo cumple cuando se eliminan. **Nota:** puede seleccionar la casilla de verificación solo si **validación de tipo Edi** está seleccionada.|  
    |**Directiva de separador final**|-Seleccione **no permite** si no desea permitir delimitadores y separadores finales en un intercambio recibido del remitente de intercambio. Si el intercambio contiene delimitadores y separadores finales, se declarará no válido.<br />-Seleccione **opcional** para aceptar intercambios con o sin delimitadores y separadores finales.<br />-Seleccione **obligatorio** si el intercambio recibido debe contener delimitadores y separadores finales.|  
  
     Puede agregar tantas filas como desee para definir la configuración de validación para intercambios específicos.  
  
     Para eliminar una configuración de validación, seleccione la fila y haga clic en **eliminar**.  
  
    > [!NOTE]
    >  Editar las propiedades de la cuadrícula puede resultar un poco difícil. En su lugar, puede seleccionar la fila que desee editar y, a continuación, edite las mismas propiedades en el **Editar fila seleccionados** sección. La configuración que proporcione aquí se refleja en la fila seleccionada.  
  
4.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar transacción configurar (X12)](../core/configuring-transaction-set-settings-x12.md)