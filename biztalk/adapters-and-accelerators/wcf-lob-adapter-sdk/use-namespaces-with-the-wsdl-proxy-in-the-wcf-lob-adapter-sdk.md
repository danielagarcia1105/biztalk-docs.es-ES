---
title: Usar espacios de nombres con el Proxy de WSDL en el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 781d20fa-83e3-42fa-866e-5650d5eb71a7
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc21b37ae80299bf5ddd78d1ca48331e1e369e78
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="use-namespaces-with-the-wsdl-proxy-in-the-wcf-lob-adapter-sdk"></a>Usar espacios de nombres con el Proxy de WSDL en el SDK de adaptador LOB de WCF
El [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] genera WSDL y servidores proxy para un adaptador con los valores suministrados por el programador mediante el [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)] o se ha especificado en el código mediante la modificación de la variable privada SERVICENAMESPACE o `Namespace` propiedad del adaptador.  
  
 Los tipos de esquema y los elementos definidos dentro de la \<WSDL: Types\>\<esquema\> use {OperationNamespace} de forma predeterminada. Si un tipo determinado tiene un TypeNamespace invalidado establecido el **TypeMetadata** objeto, ese espacio de nombres se utiliza para el tipo complejo u o definición de elemento.  
  
## <a name="impact-on-wsdl"></a>Impacto en WSDL  
 En la tabla siguiente se muestra cómo afectan los espacios de nombres diferentes en un adaptador personalizado a WSDL correspondiente. En la tabla, ~ {OperationNamespace} es la asignación de espacio de nombres de clase de un identificador URI; Por ejemplo, si es de {OperationNamespace} "myscheme://a.b/c", ~ {OperationNamespace} será myscheme.a.b.c.  
  
|Construcción WSDL|Sintaxis|  
|--------------------|------------|  
|TargetNamespace WSDL,<br /><br /> Xmlns:TS|{Custom} Adapter.Namespace|  
|\<WSDL: portType\>|{esquema de}. ~ {OperationNamespace}|  
|Nombre del mensaje de entrada de WSDL|{esquema de}. ~ {OperationNamespace} _ {OperationName} _InputMessage|  
|Nombre del mensaje de salida WSDL|{esquema de}. ~ {OperationNamespace} _ {OperationName} _OutputMessage|  
|\<WSDL: Types\>\<esquema\> targetNamespace|{esquema} :// {OperationNamespace}|  
|\<elemento\>\<complexType\>|Use {TypeNamespace} si su valor no es null o está vacío.|  
  
## <a name="impact-on-proxy"></a>Impacto en el servidor Proxy  
 Tres atributos diferentes en el proxy se ven afectados por los espacios de nombres:  
  
-   [**System.ServiceModel.ServiceContractAttribute**(nombre = "{esquema}. ~ {OperationNamespace}", Namespace="{Custom}Adapter.Namespace"]  
  
-   [**System.ServiceModel.MessageContractAttribute**(WrapperName = "DivideResponse", WrapperNamespace = "{esquema} :// {OperationNamespace}", IsWrapped = true)]  
  
-   [**System.ServiceModel.MessageBodyMemberAttribute**(Namespace = "{esquema} :// {TypeNamespace}", orden = 0)]  
  
## <a name="see-also"></a>Vea también  
 [Prácticas recomendadas de desarrollo mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)