---
title: Mediante los comandos del Editor de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e216ae5d-5bad-48ef-87d1-8aa8ee20179b
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1ae30305f5e23e99b5a0bc76cba9bfc7f451b03
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="use-biztalk-editor-commands"></a>Usar comandos de Editor de BizTalk

## <a name="overview"></a>Información general
Cuando el Editor de BizTalk se activa, agrega un menú llamado **BizTalk** a la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell. Este menú proporciona acceso a los comandos y la funcionalidad del Editor de BizTalk. Cuando el Editor de BizTalk está activo, el **BizTalk** menú proporciona los comandos que son específicos para editar esquemas de BizTalk.  
  
 Asimismo y donde procede, el Editor de BizTalk utiliza existente [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] elementos de menú para los comandos que tienen paralelismos obvios con funcionalidad de la aplicación estándar. Por ejemplo, cuando el Editor de BizTalk está activo, el **guardar** comando el **archivo** menú guarda los cambios en el esquema que se está editando actualmente.  
  
## <a name="commands-list"></a>Lista de comandos
 En la siguiente tabla se describen los comandos del Editor de BizTalk que se pueden usar en el proceso de desarrollar esquemas.  
  
|Command<br /><br /> (Ubicaciones en el menú)|Description|  
|------------------------------------|-----------------|  
|**Abrir esquema**<br /><br /> (Archivo &#124; abiertos &#124; archivo...)|Abre un esquema de BizTalk para su edición en el Editor de BizTalk.<br /><br /> También está disponible en el menú contextual del Explorador de soluciones cuando se selecciona un esquema y cuando se hace doble clic en un esquema en el Explorador de soluciones.|  
|**Cerrar esquema**<br /><br /> (Archivo &#124; cerrar)|Cierra el Editor de BizTalk para el esquema actual y solicita si se deben guardar los cambios no guardados.<br /><br /> También está disponible mediante el botón de cierre estándar en la esquina superior derecha de la ventana de edición principal de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].|  
|**Nuevo esquema**<br /><br /> (Proyecto &#124; Agregar nuevo elemento... &#124; Esquema)|Crea un nuevo esquema de BizTalk para su edición y abre el Editor de BizTalk.<br /><br /> También está disponible en el menú contextual del proyecto de BizTalk en el Explorador de soluciones (agregar &#124; nuevo elemento).|  
|**Guardar esquema**<br /><br /> (Archivo &#124; guardar schema.xsd)<br /><br /> (Archivo &#124; guardar schema.xsd como...)<br /><br /> (Archivo &#124; guardar todo)|Guarda el esquema de BizTalk que se está editando en ese momento con su propio nombre con un nombre nuevo o como parte del proceso de guardar todos los cambios no guardados, respectivamente.|  
|**Cortar, copiar, Pegar nodo**<br /><br /> (Editar &#124; cortar, editar &#124; copiar, editar &#124; pegar)|Permite **esquema** vista de árbol de nodos para mover y duplicar dentro del esquema.<br /><br /> Cuando sea aplicable, estos comandos también están disponibles en el menú contextual del nodo seleccionado y mediante el estándar de cortar, copiar y pegar teclas de método abreviado: CTRL+X, CTRL+C y CTRL+V.|  
|**Eliminar nodo**<br /><br /> (Editar &#124; eliminar)<br /><br /> (BizTalk &#124; eliminar)|Elimina el nodo seleccionado actualmente en la vista de árbol de esquema (aparece un mensaje para que confirme la acción).<br /><br /> Si corresponde, este comando también está disponible en el menú contextual del nodo seleccionado.|  
|**Buscar nodo**<br /><br /> (Editar &#124; buscar y reemplazar &#124; búsqueda rápida)|Proporciona funcionalidad de búsqueda de nombres de nodo en la vista de árbol de esquema, que puede ser útil si hay esquemas grandes.|  
|**Propiedades**<br /><br /> (Vista &#124; ventana Propiedades)<br /><br /> (BizTalk &#124; propiedades)|Proporciona acceso a las propiedades de los nodos de la vista de árbol de esquema y a objetos de nivel superior como los propios esquemas.<br /><br /> También está disponible en el menú contextual del nodo seleccionado.|  
|**Insertar nodos de esquema**<br /><br /> (BizTalk &#124; Insertar nodo de esquema &#124; *)|Proporciona una forma de insertar distintos tipos de nodos en la vista de árbol de esquema. Para obtener más información acerca de los tipos de nodos que se pueden agregar, consulte [representación de esquemas de BizTalk](../core/biztalk-representation-of-schemas.md).<br /><br /> Si es aplicable, estos comandos también están disponibles en el menú contextual del nodo seleccionado.|  
|**Promote**<br /><br /> (BizTalk &#124; promover &#124; *)|Ofrece distintas formas de promocionar las propiedades.<br /><br /> También está disponible en el menú contextual del nodo seleccionado.|  
|**Expanda el nodo de esquema**<br /><br /> (BizTalk &#124; Expandir nodo de esquema)|Expande por completo el nodo seleccionado actualmente (que está como mínimo parcialmente contraído) en la vista de árbol de esquema.<br /><br /> Si corresponde, este comando también está disponible en el menú contextual del nodo seleccionado.|  
|**Contraer nodo de esquema**<br /><br /> (BizTalk &#124; Contraer nodo de esquema)|Contrae por completo el nodo seleccionado actualmente (que está como mínimo parcialmente expandido) en la vista de árbol de esquema.<br /><br /> Si corresponde, este comando también está disponible en el menú contextual del nodo seleccionado.|  
|**Actualizar XSD**<br /><br /> (BizTalk &#124; actualizar XSD)|Actualiza la vista XSD, que se puede establecer que no se actualice automáticamente seleccionando el **desactivar actualización automática** casilla situada debajo de la vista XSD.<br /><br /> Este comando también está disponible en el menú contextual del nodo seleccionado y haga clic en **actualizar** debajo de la vista XSD.|  
|**Rename**<br /><br /> (BizTalk &#124; cambiar el nombre)|Permite **registro**, **atributo de campo**, y **elemento de campo** nodos se va a cambiar, en su lugar, dentro de la vista de árbol de esquema.<br /><br /> Este comando es equivalente a cambiar la **nombre de nodo** propiedad del nodo seleccionado.<br /><br /> Si corresponde, este comando también está disponible en el menú contextual del nodo seleccionado.|  
|**Opciones del Editor de BizTalk**<br /><br /> (Herramientas &#124; opciones &#124; el Editor de BizTalk)|Permite la configuración de los cuadros de diálogo de confirmación (activar o desactivar), así como ajustar la fuente y el color de fondo.|  
  
 La siguiente tabla describe comandos de esquema adicionales que están disponibles en el menú contextual del esquema seleccionado en el Explorador de soluciones.  
  
|Comando de esquema|Description|  
|--------------------|-----------------|  
|**Abrir**|Abre el esquema seleccionado en el Editor de BizTalk.|  
|**Abrir con**|Permite abrir el esquema seleccionado en distintos editores XSD, incluido el Editor de BizTalk.|  
|**Validar esquema**|Valida el esquema seleccionado.|  
|**Validar instancia**|Valida la instancia especificada por el **nombre de archivo de instancia de entrada** propiedad en Visual Studio **propiedades** ventana con respecto al esquema seleccionado.|  
|**Generar instancia**|Genera una instancia del esquema seleccionado con el nombre de archivo especificado por el **nombre de archivo de instancia de salida** propiedad en Visual Studio **propiedades** ventana.<br /><br /> Si no se especifica ningún nombre para la instancia de salida generada, se utilizará un nombre de archivo predeterminado. El nombre de archivo predeterminado es el nombre del archivo de esquema antepuesto a la cadena "_output.xml" de la carpeta _SchemaData de una carpeta temporal de la carpeta Documents and Settings.|  
|**Ver código**|Muestra el XSD subyacente.|  
|**Diseñador de vistas**|Abre el esquema en el Diseñador de esquemas XML de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].|  
|**Excluir del proyecto**|Quita el esquema que esté seleccionado en ese momento del proyecto actual de BizTalk.<br /><br /> Use la **Agregar elemento existente** comando para volver a agregar un esquema que se excluyó previamente del proyecto de BizTalk actual.|  
|**Cortar, copiar, pegar**|Utilice estos comandos para realizar el estándar [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] comportamiento de cortar, copiar y pegar esquemas enteros dentro de un proyecto de BizTalk.|  
|**Eliminar**|Elimina de forma permanente el esquema seleccionado actualmente (aparece un mensaje para que confirme la acción).|  
|**Rename**|Permite cambiar el nombre del esquema seleccionado en ese momento, en la posición actual.|  
|**Propiedades**|Se abre Visual Studio **propiedades** ventana para el esquema seleccionado actualmente, en el que algunas de las propiedades del esquema pueden examinarse y definirse. <br/><br/>**Nota:** otras propiedades del esquema se examina y se configuran el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades cuando se selecciona el esquema. Propiedades que se establecen en los **propiedades** ventana son aquellas propiedades para el que diferentes pueden tener valores para un mismo esquema cuando se usa en más de un proyecto de BizTalk. <br /><br /> Para obtener más información acerca de cómo establecer las propiedades de esquema y las propiedades de esquemas, consulte [archivo de esquema de configuración y las propiedades de elemento de esquema](../core/how-to-set-schema-file-and-schema-item-properties.md) y **propiedades de archivo de esquema** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].|  
  
## <a name="see-also"></a>Vea también  
 [Usar el Editor de BizTalk](../core/using-biztalk-editor.md)