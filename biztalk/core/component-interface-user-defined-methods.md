---
title: Los métodos definidos por el usuario de interfaz de componente | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, user-defined methods
- user-defined methods, component interface
- custom component interfaces, limitations
- collection limitations
- custom methods, samples
- samples, custom methods
- component interfaces, limitations for custom CI
ms.assetid: e4b15889-35ff-44aa-819d-eade9690bdd6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68149876dc51d90b4dbc07772fd9b9b5c60fb7db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022570"
---
# <a name="component-interface-user-defined-methods"></a>Métodos definidos por el usuario de interfaz de componente
El adaptador de Microsoft BizTalk para PeopleSoft Enterprise admite métodos definidos por el usuario en interfaces de componentes. Las firmas son del tipo:  
  
```  
myRet=myCI.myMethod(parameter1, parameter2, ...)  
```  
  
 donde:  
  
- `parameter1`, `parameter2` son parámetros de entrada.  
  
- `myRet` es el valor devuelto.  
  
  Los parámetros solo pueden ser parámetros de entrada del método. Solo se puede devolver un valor desde el método como parámetro de devolución.  
  
> [!NOTE]
>  La interfaz de componente que contiene métodos definidos por el usuario solo debería tener la función `Get` de PeopleSoft habilitada. Si la interfaz de componente tiene claves, no funcionarán los métodos personalizados.  
  
## <a name="custom-ci-limitation"></a>Limitación del elemento de configuración personalizado  
 El adaptador de BizTalk para PeopleSoft Enterprise puede controlar métodos de PeopleSoft proporcionados para los que la interfaz de componente no tiene claves. Si la interfaz de componente tiene claves, los métodos personalizados no funcionará.  
  
### <a name="workaround"></a>Solución  
 Cree una nueva interfaz de componente que no tenga claves y escriba un nuevo método personalizado que incorpore las claves como parte de los parámetros de llamada. Por ejemplo, se puede usar el método personalizado SetPassword en la interfaz de componente USER_PROFILE; sin embargo, USER_PROFILE tiene claves. Puede crear una nueva interfaz de componente sin claves y, a continuación, crear un método personalizado en esta interfaz. Este método aceptaría dos parámetros, ID de usuario y contraseña. El método personalizado podría invocar entonces USER_PROFILE con un `Get` y, a continuación, invocar `SetPassword`. Para obtener más detalles, consulte la documentación de PeopleSoft.  
  
 A causa de una limitación de PeopleSoft, los tipos `Date`, `DateTime` y `Time` que aparecen en los métodos definidos por el usuario se asignan como cadenas en el código de cliente.  
  
## <a name="collection-limitation"></a>Limitación de la colección  
 Los métodos definidos por el usuario no pueden devolver ninguna colección, o incluso más generalmente, ningún objeto de API. Esto significa que solo pueden devolver tipos simples, por ejemplo, cadenas y números. Puede evitarse esta limitación si se envía una colección como cadena XML y se programa el cliente para que analice las cadenas para extraer los elementos en el formato correcto. Puede examinar la interfaz del componente personalizado GET_CI_INFO para ver un ejemplo de esta solución.  
  
## <a name="sample-custom-method"></a>Método personalizado de ejemplo  
 Puede usar el siguiente método personalizado básico, SayHello, para probar la funcionalidad de la interfaz de componente mediante métodos personalizados.  
  
 La siguiente función de PeopleCode es un método definido por el usuario de una interfaz de componente de PeopleSoft denominada ACB_EMPLOYEE. El ejemplo devuelve una cadena donde el valor devuelto es **Hello** seguido del valor del parámetro de entrada.  
  
```  
Function SayHello(&sName As string) Returns string  
      &EOL = Char(10);  
      &sResult = "Hello " | &sName | &EOL;  
      Return &sResult;  
End-Function;  
```  
  
> [!NOTE]
>  Para modificar múltiples tablas al mismo tiempo (mediante un comando) puede crear otra interfaz de componente o un método definido por el usuario para la interfaz de componente.  
  
## <a name="see-also"></a>Vea también  
 [Apéndice A: Métodos de interfaces de componentes](../core/appendix-a-component-interface-methods.md)