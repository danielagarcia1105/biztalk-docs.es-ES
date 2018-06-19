---
title: Cómo importar BPEL4WS | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3626fcb9-8e7d-4812-a0c9-bde6e7954ec8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e82dd80e280eff39ff5c1678b5c9751e378ee1b
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
ms.locfileid: "31008479"
---
# <a name="import-bpel4ws-in-biztalk-server"></a>Importar BPEL4WS en BizTalk Server
Puede importar desde el lenguaje BPEL4WS existente para crear una orquestación.  
  
> [!IMPORTANT]
>  Esta versión de BizTalk Server es compatible con BPEL4WS 1.1. No es compatible con BPEL4WS 1.0 para realizar importaciones o exportaciones.  
  
 Para obtener un ejemplo de cómo importar BPEL4WS, consulte [BPEL importar (ejemplo de BizTalk Server)](../core/bpel-import-biztalk-server-sample.md).  
  
## <a name="import-bpel4ws-into-an-orchestration"></a>Importar BPEL4WS a una orquestación  
  
1.  Cree un nuevo proyecto.  
  
2.  En los tipos disponibles en Proyecto de BizTalk, haga doble clic en Proyecto de importación BPEL de servidor BizTalk Server, o bien seleccione Proyecto de importación BPEL de servidor BizTalk Server y haga clic en Aceptar.  
  
3.  En el asistente, seleccione los archivos BPEL, WSDL y XSD que se deben importar para crear el nuevo proyecto de BizTalk. Incluya todos los archivos a los que se hace referencia mediante las instrucciones import e include.  
  
4.  Seleccione los archivos WSDL para los servicios Web invocados.  
  
     Ahora puede modificar o implementar la nueva orquestación.  
  
 **Restricciones de importación de BPEL4WS**  
  
-   Al importar BPEL y WSDL, asegúrese de que la propiedad de nombre del nodo de definición WSDL y el nodo de proceso BPEL no coinciden.  
  
-   No utilice palabras reservadas para XLANG/s en BPEL4WS cuando realice la importación. Para obtener una lista completa, consulte [palabras reservadas de XLANG/s](../core/xlang-s-reserved-words.md).  
  
-   solo los tipos simples XSD predefinidos son compatibles.  
  
-   xsd: QName no es compatible; se importa como System.String. Utilice en su lugar xsd: String.  
  
-   Considere usar XPath canónicos al importar con BPEL4WS.  
  
     Se recomienda importar solamente XPath canónicos para obtener un rendimiento óptimo. La ruta de acceso completa de la raíz al nodo promocionado se debe especificar mediante '/*[local-name()="someName" y namespace-uri()="someUri"]'.  
  
     Si importa un XPath no canónico, puede quitar una promoción y volver a promocionar el mismo campo para que el editor de esquemas cree el XPath canónico correcto.  
  
     Ejemplo: (targetNamespace = http://BizTalk_Server_Project3.Schema1)  
  
    ```  
    <element name=Root type=complexType>  
                <sequence>  
                            <element name=promotedField/>  
                </sequence>  
    </element>  
    ```  
  
     `XPath - /*[local-name()='Root' and namespace-uri()='http://BizTalk_Server_Project3.Schema1']/\*[local-name()='promotedField' and namespace-uri()='']` 
  
    |XPath canónico|XPath no canónico|  
    |---------------------|--------------------------|  
    |El Editor de BizTalk muestra un icono especial (![](../core/media/ebiz-orch-promotedprop.gif "ebiz_orch_promotedprop")) para indicar que se ha promocionado el campo. El uso de expresiones XPath canónicas para promocionar campos mejora el rendimiento a través del recorrido más eficaz de XML.|El Editor de BizTalk no muestra ningún icono especial. Tanto el compilador como el cuadro de diálogo de promoción presentan advertencias. Hay un efecto lineal, aunque no trivial, sobre el rendimiento a medida que aumenta el tamaño del mensaje.|  
  
## <a name="see-also"></a>Vea también  
 [Cómo exportar BPEL4WS](../core/how-to-export-bpel4ws.md)   
 [Conversiones de tipos de XLANG/s a BPEL4WS](../core/xlang-s-to-bpel4ws-type-conversions.md)
