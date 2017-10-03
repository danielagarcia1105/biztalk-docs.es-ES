---
title: Retirar | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], TypedData table
- Retract function [Business Rules Engine], TypedXMLDocument
- Retract function [Business Rules Engine]
- Retract function [Business Rules Engine], DataConnection
- Retract function [Business Rules Engine], .NET objects
- .NET objects
ms.assetid: 24b6b894-6810-4497-a122-8c91f0b2e816
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17eb4739412d310d2a69b53c8470abc7461ce3ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="retract"></a>Retirar
Puede usar el **Retract** function para quitar objetos de memoria de trabajo del motor de reglas de negocios. En los párrafos siguientes se describe el comportamiento asociado con la retirada de entidades de tipos diferentes de la memoria de trabajo del motor de reglas.  
  
## <a name="net-objects"></a>Objetos .NET  
 Un objeto .NET se retira en una directiva mediante el uso de la **Retract** función. Esta función está disponible en el Compositor de reglas de negocio como un **funciones** elemento de vocabulario: arrastre la clase (no el ensamblado o un método) a la **Retract** parámetro.  
  
> [!NOTE]
>  Si se arrastra un método en el **Retract** función, el motor intenta retirar el objeto devuelto por el método.  
  
 Retirar un objeto .NET lo quita de la memoria de trabajo del motor de reglas y tiene el impacto siguiente:  
  
-   Las acciones de las reglas que utilizan el objeto en un predicado se retiran de la agenda (de existir alguna en la agenda).  
  
-   Las acciones de la agenda que utilizan los objetos se quitan de la agenda.  
  
    > [!NOTE]
    >  Otras acciones más arriba en la agenda pueden haber ejecutado ya antes de la **Retract** se llamó la función.  
  
-   El objeto ya no es evaluado por el motor.  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 Puede retirar el original **TypedXmlDocument** que se imponen en el motor o retirar uno de los secundarios **TypedXmlDocument**creado a partir de un nodo del elemento primario **XmlDocument** .  
  
 Utilizando el código XML siguiente como ejemplo, puede retirar el **TypedXmlDocument** asociados con el pedido o uno o ambos de los **TypedXmlDocument**que están asociadas con la orderline.  
  
```  
<order>  
   <orderline customer="Joe" linenumber="001">  
      <product name="router" quantity="10" cost="550" />  
   </orderline>  
   <orderline customer="Jane" linenumber="002">  
      <product name="switch" quantity="1" cost="300" />  
   </orderline>  
</order>  
```  
  
 Para retirar el objeto de pedido, arrastre el nodo superior del esquema en el panel de hechos Esquemas XML. Este nodo finaliza en ".xsd" y representa el nodo raíz del documento (no el nodo de elemento de documento); tiene un selector "/" que hace referencia a la inicial **TypedXmlDocument**. Cuando el elemento primario **TypedXmlDocument** se retira, todos los **TypedXmlDocument** instancias asociadas a la **TypedXmlDocument** (todos los  **TypedXmlDocument**s se creó mediante una llamada a la **Assert** función basándose en los selectores utilizados en la directiva) se quitan de la memoria de trabajo.  
  
 Para retirar solo un elemento secundario individual **TypedXmlDocument** (que es una orderline), puede arrastrar este nodo desde el panel de esquemas XML en la **Retract** función. Es importante tener en cuenta que todos los **TypedXmlDocument**s están asociados con el nivel superior **TypedXmlDocument** que se impuso originalmente y no con la **TypedXmlDocument**que aparece por encima de él en la jerarquía del árbol XML. Por ejemplo, el producto es un **TypedXmlDocument** por debajo del objeto orderline; por lo tanto, estará asociado con el orden de **TypedXmlDocument**y no con la orderline  **TypedXmlDocument**. En la mayoría de los casos, esta distinción no es importante. Sin embargo, si retira el objeto de pedido, también se retiran los objetos de producto y la orderline. Si retira el objeto de la orderline, solo se retira ese objeto y no el objeto de producto.  
  
 El motor solo funciona con y realiza un seguimiento de instancias de un objeto (**TypedXmlDocument**s) que creó cuando el **TypedXmlDocument** se impuso inicialmente. Si crea nodos adicionales, por ejemplo, nodos del mismo nivel a un nodo que se seleccionó a través de un selector en la directiva, estos nodos no se evalúan en las reglas a menos que **TypedXmlDocument**s se crean y se imponen para ellos. Imponer estos nuevos, de nivel inferior **TypedXmlDocuments** hace que se evalúen en las reglas, pero el nivel superior **TypedXmlDocument** no tiene conocimiento de ellos. Cuando el nivel superior **TypedXmlDocument** se retira, el impuesto de forma independiente nuevo **TypedXmlDocument**isl s no se retira automáticamente. Como resultado, si se crean nuevos nodos, normalmente es más sencillo retirar y volver a imponer el completo **XmlDocument**.  
  
 El **TypedXmlDocument** clase es compatible con una serie de métodos útiles que se puede llamar dentro de un miembro de .NET personalizado como parte de una acción. Éstos incluyen la capacidad para obtener el **XmlNode** asociados con el **TypedXmlDocument** o el elemento primario **TypedXmlDocument**.  
  
## <a name="typeddatatable"></a>TypedDataTable  
 Se puede retirar ninguno de los dos **TypedDataRow**s o todo el **TypedDataTable**. Si retira una tabla, todas las filas que lo contiene se retiran de la memoria de trabajo.  
  
 Para retirar toda la **TypedDataTable** debe usar una función auxiliar para obtener acceso a la **primario** propiedad **TypedDataRow**, por ejemplo:  
  
```  
Retract(MyHelper.GetTypedDataTable(TypedDataRow))  
```  
  
 En la acción anterior, arrastre la tabla en **TypedDataRow**. En **GetTypedDataTable** devolvería el valor de **TypedDataRow.Parent**.  
  
 Al igual que con **TypedXmlDocument**s, si valida adicionales, nuevo **TypedDataRow**s para el mismo **DataTable** después de validar la **TypedDataTable**, se tratan como entidades individuales y retirar el **TypedDataTable** no da como resultado la retracción de estos adicional **TypedDataRow**s. Solo el **TypedDataRow**contenidos en el **TypedDataTable** al se impuso se retiran.  
  
## <a name="dataconnection"></a>DataConnection  
 Cuando un **DataConnection** se retira, todos los **TypedDataRow**s recuperados de la base de datos a través de la consulta construida por la **DataConnection** se retiran de memoria de trabajo. El **DataConnection** propio también se retira, lo que significa que no hay más **TypedDataRow**s que se va a recuperar a través de la **DataConnection** (es decir, mediante el uso de la  **DataConnection** en otros predicados o acciones).  
  
 Cuando se usa un **DataConnection**, cualquier operación de retirada de un individuo **TypedDataRow** pone el motor en un estado incoherente. Por lo tanto, no se permiten operaciones en persona **TypedDataRow**que están asociadas a un **DataConnection**. Si arrastra la tabla (mediante la **DataConnection** parámetro) en el **Retract** función, estará retirando la **DataConnection**.  
  
## <a name="see-also"></a>Vea también  
 [Funciones de Control del motor](../core/engine-control-functions.md)