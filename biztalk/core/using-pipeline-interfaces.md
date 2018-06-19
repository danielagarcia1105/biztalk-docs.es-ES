---
title: Usar Interfaces de canalización | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb88d0d-23ab-4fdb-bcd2-56050456cf69
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c365a8d7bdf37564d3d9b2dceac1c8615e126ebc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289148"
---
# <a name="using-pipeline-interfaces"></a>Utilizar Interfaces de canalizaciones
Un componente de canalización consiste en un componente .NET o COM que implementa un conjunto de interfaces predefinidas para la interacción con el motor de mensajería de BizTalk. Según sea la funcionalidad del componente, se deberán implementar diferentes interfaces. En este tema se tratan estas interfaces y algunos de sus métodos.  
  
> [!WARNING]
>  Si está creando un componente de canalización personalizado mediante COM, debe configurarlo para utilizar el modelo de subprocesamiento controlado múltiple (MTA, Multi-Threaded Apartment). En caso contrario, se producirá un error en la invocación del componente con un error E_NOINTERFACE.  
  
## <a name="ipipelinecontext"></a>IPipelineContext  
 Pueden usar todos los componentes de canalización **IPipelineContext** métodos para tener acceso a todas las interfaces específicas de procesamiento de documentos. El **IPipelineContext** interfaz proporciona las siguientes funcionalidades:  
  
-   Permite que los componentes recuperen la configuración de canalización y fase de ambiente.  
  
-   Permite que los componentes recuperen mensajes y generadores de mensajes. Con estos generadores, los componentes pueden crear diversos objetos necesarios para la ejecución del componente.  
  
-   Permite que los componentes recuperen las especificaciones del documento. Una especificación de documento es un esquema XSD más anotaciones adicionales.  
  
## <a name="ibasecomponent"></a>IBaseComponent  
 Todos los componentes de la canalización necesitan implementar esta interfaz para proporcionar información básica sobre el componente.  
  
## <a name="icomponent"></a>IComponent  
 Todos los componentes de la canalización, excepto ensambladores y desensambladores, implementan esta interfaz con el fin de recibir mensajes del motor de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para su proceso y de volver a enviar los mensajes procesados al motor.  
  
 **Ejecutar.** método al que llama el motor para pasar el mensaje de entrada al componente y recuperar el mensaje procesado del componente.  
  
## <a name="ipropertybag-ipersistpropertybag"></a>IPropertyBag, IPersistPropertyBag  
 Componentes de canalización necesitan implementar **IPersistPropertyBag** para recibir su información de configuración. Esta interfaz y **IPropertyBag** son las interfaces estándares. Para obtener más información acerca de estas interfaces, consulte la documentación del kit de desarrollo de software (SDK) de Microsoft .NET Framework.  
  
## <a name="idisassemblercomponent"></a>IDisassemblerComponent  
 Un componente de desensamblado es un componente de canalización que recibe un mensaje en la entrada y produce cero o más mensajes en la salida. Los componentes de desensamblado se utilizan para dividir intercambios de mensajes en documentos individuales. Un componente de desensamblador debe implementar los métodos de la **IDisassemblerComponent** interfaz recibir mensajes desde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para su procesamiento y para pasar desensamblado documentos volver a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
|Método|Description|  
|------------|-----------------|  
|**Desensamblar**|Realiza el desensamblado del documento entrante **pInMsg**.|  
|**GetNext**|Obtiene el mensaje siguiente del conjunto de mensajes que dan como resultado de ejecución del desensamblador. Devuelve **NULL** si no hay ningún mensaje más.|  
  
 Si está escribiendo un componente de desensamblador que vaya a admitir el procesamiento de intercambio recuperable, debe hacer lo siguiente:  
  
1.  Permitir las búsquedas en secuencias de entrada incluyéndolas en una VirtualStream().  
  
2.  En GetNext(), hacer que la lógica determine cuando un mensaje no es válido. Si un mensaje no es válido, defina BTS.MessageDestination = "SuspendQueue" y vuelva al mensaje en GetNext().  
  
3.  Si el mensaje es válido, defina BTS.SuspendMessageOnRoutingFailure = True y vuelva al mensaje en GetNext().  
  
## <a name="iassemblercomponent"></a>IAssemblerComponent  
 Un componente de ensamblado es un componente de canalización que recibe varios mensajes en la entrada y produce un mensaje en la salida. Los componentes de ensamblado se utilizan para recopilar documentos individuales en el lote de intercambio de mensajes.  
  
> [!NOTE]
>  En esta versión de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], no se utiliza la funcionalidad de ensamblado, por lo que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] siempre transfiere un documento a la entrada del componente.  
  
 Un componente de ensamblador implementa los **IAssemblerComponent** métodos llamados por el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] motor en tiempo de ejecución.  
  
|Método|Description|  
|------------|-----------------|  
|**AddDocument**|Agrega el documento **pInMsg** a la lista de mensajes que se incluirán en el intercambio.|  
|**Ensamblar**|Crea el intercambio a partir de los mensajes agregados mediante el método anterior. Devuelve un puntero al mensaje ensamblado.|  
  
## <a name="iprobemessage"></a>IProbeMessage  
 Un componente de canalización (general, ensamblado o desensamblado) puede implementar **IProbeMessage** si requiere la funcionalidad de búsqueda de mensajes. Un componente de búsqueda se utiliza en las fases de canalización que tienen **FirstMatch** modo de ejecución. En tales fases, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entrega el mensaje al componente y la **sondeo** método examina el comienzo del mensaje para determinar si el componente identifica el formato del mensaje.  
  
|Método|Description|  
|------------|-----------------|  
|**Sondeo**|Este método toma **pInMsg** mensaje y devuelve **True** si se reconoce el formato o **False** en caso contrario.|  
  
## <a name="inameditem"></a>INamedItem  
 Se trata de una interfaz auxiliar para tener acceso a los esquemas de documentos a partir del código administrado y sin administrar.  
  
## <a name="inameditemlist"></a>INamedItemList  
 Se trata de una interfaz auxiliar para tener acceso a los esquemas de documentos a partir del código administrado y sin administrar.  
  
## <a name="idocumentspec"></a>IDocumentSpec  
 Componentes de canalización pueden utilizar métodos de la **IDocumentSpec** de la interfaz para realizar acciones específicas del documento, como mover propiedades de contenido al contexto y viceversa, tener acceso a los esquemas de documento y así sucesivamente.  
  
|Método|Description|  
|------------|-----------------|  
|**Tipo de documento**|Devuelve el tipo del documento actual.|  
|**DocSpecName**|Devuelve el nombre de especificación del documento actual.|  
|**GetSchemaCollection**|Devuelve la lista de esquemas de documento correspondiente al documento actual.|  
|**GetBodyPath**|Devuelve la XPath al nodo en el documento en el que comienza la parte del cuerpo.|  
|**GetDistinguishedPropertyAnnotationEnumerator**|Devuelve un enumerador de diccionarios de todas las anotaciones de propiedades de campos distintivos.|  
|**GetPropertyAnnotationEnumerator**|Devuelve un enumerador de todas las anotaciones de propiedades.|  
  
## <a name="icomponentui"></a>IComponentUI  
 Los componentes de la canalización deben implementar esta interfaz para su uso en el entorno del Diseñador de canalizaciones.  
  
|Método|Description|  
|------------|-----------------|  
|**Icono**|Proporciona el icono asociado a este componente.|  
|**Validar**|El Diseñador de canalizaciones llama a este método antes de la compilación de canalizaciones para comprobar que todas las propiedades de configuración están definidas correctamente.|  
  
 El **icono** propiedad devuelve un **IntPtr**. En el ejemplo de C# siguiente se muestra cómo devolver un **IntPtr**.  
  
```csharp  
static   ResourceManager resManager = new ResourceManager("ResourceManager", Assembly.GetExecutingAssembly());  
...  
[Browsable(false)]  
public IntPtr Icon  
{  
   get  
   {  
      return ((Bitmap)resManager.GetObject("MyIcon")).GetHicon();  
   }  
}  
```  
  
 Para obtener más información, consulte **interfaz IComponentUI (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]. 
  
## <a name="see-also"></a>Vea también  
 [Desarrollar componentes de canalización personalizado](../core/developing-custom-pipeline-components.md)   
 [CustomComponent (ejemplo de BizTalk Server)](../core/customcomponent-biztalk-server-sample.md)