---
title: Extender las enumeraciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enumeration values
- 2.X schemas, enumeration values
ms.assetid: 043def35-b644-4502-a2e2-cc1a5fc0328a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc5b91513833b76ba7dc3697f9eee409bf9752bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987853"
---
# <a name="extending-enumerations"></a>Extender las enumeraciones
Puede agregar valores a las enumeraciones que establecer los valores aceptados para muchos tipos de datos, segmentos y campos en el cuerpo del mensaje HL7, confirmación y esquemas de cuerpo del mensaje. Esto implica cambiar el conjunto de valores en una tabla específica en el archivo de esquema de los valores de tabla común para la versión de HL7 en el que está trabajando (el **Tablevalues_\<**<em>versión</em>  **\>.xsd** archivo de esquema).  
  
 Agregar a la enumeración de forma diferente para el esquema de encabezado de mensaje a como lo hace en otro esquema, como el esquema de cuerpo del mensaje. Para el esquema de encabezado de mensaje, debe cambiar la tabla en el archivo MSH_25_GLO_DEF.xsd. Para otros esquemas, cambia la tabla en el archivo de esquema de los valores de tabla (tablevalues_\<versión\>.xsd).  
  
### <a name="to-add-an-enumeration-value-to-the-table-values-common-schema-file"></a>Para agregar un valor de enumeración para el archivo de esquema común de valores de tabla  
  
1. En primer lugar, deberá determinar la tabla que contiene la enumeración que se desea agregar a. En el Explorador de soluciones de Visual Studio, abra el archivo de esquema que contiene el elemento que desea cambiar. En el Explorador de BizTalk, haga clic en el elemento de campo que desea agregar un valor para.  
  
   > [!NOTE]
   >  Al cambiar una enumeración en el archivo de esquema común de valores de tabla, todos los objetos que hacen referencia a dicha enumeración se ven afectados.  
  
2. En el **propiedades** panel, tenga en cuenta el nombre de la tabla en la **Base Data Type** campo.  
  
   > [!NOTE]
   >  Si no hay ninguna tabla se enumeran en **Base Data Type** campo y el **Derived By** propiedad no está establecida en **Restricted**, significa que el campo no tiene una enumeración asociada con él .  
  
3. En el Explorador de soluciones, abra el **Tablevalues_\<**<em>versión</em>**\>.xsd**y, a continuación, haga clic en **abrir**.  
  
   > [!NOTE]
   >  Debe realizar este procedimiento por separado para cada versión del esquema HL7 que desea cambiar.  
  
4. En el Editor de BizTalk, vaya a la tabla que desea cambiar y, a continuación, haga clic en ese nodo de tabla.  
  
5. En la ventana Propiedades, en el **restricción** sección, haga clic en **enumeración**y, a continuación, haga clic en el botón de puntos suspensivos (...) para abrir el Editor de enumeración.  
  
6. En el Editor de enumeración, agregar el nuevo valor a la lista de valores existentes y, a continuación, haga clic en **Aceptar**.  
  
### <a name="to-add-an-enumeration-value-to-a-message-header-schema"></a>Para agregar un valor de enumeración a un esquema de encabezado de mensaje  
  
1. En el Explorador de soluciones, abra el esquema MSH_25_GLO_DEF y, a continuación, haga clic en **abrir**.  
  
2. Haga clic en el **MSH** nodo, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **elemento de campo secundario**. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Agrega un nodo de campo a MSH, llamado **campo**. Haga clic en **ENTRAR**.  
  
3. En el **propiedades** ventana, haga clic en el **tipo de datos** nodo, a continuación, desde la lista desplegable, seleccione la tabla a la que desea agregar el valor de enumeración.  
  
4. En el **propiedades** ventana, en el **restricción** sección, haga clic en **enumeración**y, a continuación, haga clic en el botón de puntos suspensivos (...) para abrir el Editor de enumeración.  
  
5. En el Editor de enumeración, agregar el nuevo valor a la lista de valores existentes y, a continuación, haga clic en **Aceptar**.  
  
    Cuando agrega un valor a la enumeración de cualquier nodo, como el **campo** nodo, se agrega ese valor globalmente para todos los objetos que utilicen esa tabla. Como resultado, ahora puede eliminar el **campo** nodo y el valor seguirán estando presentes en la tabla. Para comprobarlo, desplazamiento en el panel derecho del Editor de BizTalk a la tabla y comprobar que el valor que ha agregado está presente.  
  
6. Haga clic en el **campo** nodo en el Editor de BizTalk, haga clic en **eliminar**y, a continuación, haga clic en **Sí**.  
  
## <a name="see-also"></a>Vea también  
 [Valores de tabla de esquemas comunes](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)   
 [Extender esquemas HL7 2.X con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [Creación de segmentos Z declarados](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [Creación de tipos de datos personalizados en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [Creación de tablas personalizadas en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)   
 [Control de segmentos de Z no declarados](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)