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
# <a name="component-interface-user-defined-methods"></a><span data-ttu-id="8f4c8-102">Métodos definidos por el usuario de interfaz de componente</span><span class="sxs-lookup"><span data-stu-id="8f4c8-102">Component Interface User-Defined Methods</span></span>
<span data-ttu-id="8f4c8-103">El adaptador de Microsoft BizTalk para PeopleSoft Enterprise admite métodos definidos por el usuario en interfaces de componentes.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise supports user-defined methods in component interfaces.</span></span> <span data-ttu-id="8f4c8-104">Las firmas son del tipo:</span><span class="sxs-lookup"><span data-stu-id="8f4c8-104">The signatures are of the form:</span></span>  
  
```  
myRet=myCI.myMethod(parameter1, parameter2, ...)  
```  
  
 <span data-ttu-id="8f4c8-105">donde:</span><span class="sxs-lookup"><span data-stu-id="8f4c8-105">where:</span></span>  
  
- <span data-ttu-id="8f4c8-106">`parameter1`, `parameter2` son parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-106">`parameter1`, `parameter2` are input parameters.</span></span>  
  
- <span data-ttu-id="8f4c8-107">`myRet` es el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-107">`myRet` is the return value.</span></span>  
  
  <span data-ttu-id="8f4c8-108">Los parámetros solo pueden ser parámetros de entrada del método.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-108">The parameters can only be input parameters to the method.</span></span> <span data-ttu-id="8f4c8-109">Solo se puede devolver un valor desde el método como parámetro de devolución.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-109">Only one value can be returned from the method as the return parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f4c8-110">La interfaz de componente que contiene métodos definidos por el usuario solo debería tener la función `Get` de PeopleSoft habilitada.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-110">The component interface that contains user-defined methods should only have the PeopleSoft `Get` function enabled.</span></span> <span data-ttu-id="8f4c8-111">Si la interfaz de componente tiene claves, no funcionarán los métodos personalizados.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-111">If the component interface has keys, then custom methods will not work.</span></span>  
  
## <a name="custom-ci-limitation"></a><span data-ttu-id="8f4c8-112">Limitación del elemento de configuración personalizado</span><span class="sxs-lookup"><span data-stu-id="8f4c8-112">Custom CI Limitation</span></span>  
 <span data-ttu-id="8f4c8-113">El adaptador de BizTalk para PeopleSoft Enterprise puede controlar métodos de PeopleSoft proporcionados para los que la interfaz de componente no tiene claves.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-113">BizTalk Adapter for PeopleSoft Enterprise can handle custom PeopleSoft methods provided that the component interface does not have keys.</span></span> <span data-ttu-id="8f4c8-114">Si la interfaz de componente tiene claves, los métodos personalizados no funcionará.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-114">If the component interface has keys, custom methods will not work.</span></span>  
  
### <a name="workaround"></a><span data-ttu-id="8f4c8-115">Solución</span><span class="sxs-lookup"><span data-stu-id="8f4c8-115">Workaround</span></span>  
 <span data-ttu-id="8f4c8-116">Cree una nueva interfaz de componente que no tenga claves y escriba un nuevo método personalizado que incorpore las claves como parte de los parámetros de llamada.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-116">Create a new component interface that does not have keys, and write a new custom method that incorporates the keys as part of the calling parameters.</span></span> <span data-ttu-id="8f4c8-117">Por ejemplo, se puede usar el método personalizado SetPassword en la interfaz de componente USER_PROFILE; sin embargo, USER_PROFILE tiene claves.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-117">For example, you could use the SetPassword custom method in the USER_PROFILE component interface; however USER_PROFILE has keys.</span></span> <span data-ttu-id="8f4c8-118">Puede crear una nueva interfaz de componente sin claves y, a continuación, crear un método personalizado en esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-118">You can create a new component interface that has no keys, and then create a custom method in your new component interface.</span></span> <span data-ttu-id="8f4c8-119">Este método aceptaría dos parámetros, ID de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-119">This method would accept two parameters, user ID and password.</span></span> <span data-ttu-id="8f4c8-120">El método personalizado podría invocar entonces USER_PROFILE con un `Get` y, a continuación, invocar `SetPassword`.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-120">The custom method could then invoke USER_PROFILE with a `Get` and then invoke `SetPassword`.</span></span> <span data-ttu-id="8f4c8-121">Para obtener más detalles, consulte la documentación de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-121">Consult the PeopleSoft documentation for more details.</span></span>  
  
 <span data-ttu-id="8f4c8-122">A causa de una limitación de PeopleSoft, los tipos `Date`, `DateTime` y `Time` que aparecen en los métodos definidos por el usuario se asignan como cadenas en el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-122">Due to a limitation in PeopleSoft, `Date`, `DateTime`, and `Time` types appearing in user-defined methods are mapped as strings in the client code.</span></span>  
  
## <a name="collection-limitation"></a><span data-ttu-id="8f4c8-123">Limitación de la colección</span><span class="sxs-lookup"><span data-stu-id="8f4c8-123">Collection Limitation</span></span>  
 <span data-ttu-id="8f4c8-124">Los métodos definidos por el usuario no pueden devolver ninguna colección, o incluso más generalmente, ningún objeto de API.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-124">User-defined methods cannot return a collection, or more generally, any API object.</span></span> <span data-ttu-id="8f4c8-125">Esto significa que solo pueden devolver tipos simples, por ejemplo, cadenas y números.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-125">This means that you can only return simple types, for example, strings and numbers.</span></span> <span data-ttu-id="8f4c8-126">Puede evitarse esta limitación si se envía una colección como cadena XML y se programa el cliente para que analice las cadenas para extraer los elementos en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-126">You can get around this limitation by sending a collection as an XML string and programming the client to parse the strings to extract the items into the correct format.</span></span> <span data-ttu-id="8f4c8-127">Puede examinar la interfaz del componente personalizado GET_CI_INFO para ver un ejemplo de esta solución.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-127">You can examine the GET_CI_INFO custom component interface to see an example of this workaround.</span></span>  
  
## <a name="sample-custom-method"></a><span data-ttu-id="8f4c8-128">Método personalizado de ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f4c8-128">Sample Custom Method</span></span>  
 <span data-ttu-id="8f4c8-129">Puede usar el siguiente método personalizado básico, SayHello, para probar la funcionalidad de la interfaz de componente mediante métodos personalizados.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-129">You can use the following basic custom method, SayHello, to test the functionality of your component interface using custom methods.</span></span>  
  
 <span data-ttu-id="8f4c8-130">La siguiente función de PeopleCode es un método definido por el usuario de una interfaz de componente de PeopleSoft denominada ACB_EMPLOYEE.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-130">The following PeopleCode function is a user-defined method of a PeopleSoft component interface named ACB_EMPLOYEE.</span></span> <span data-ttu-id="8f4c8-131">El ejemplo devuelve una cadena donde el valor devuelto es **Hello** seguido del valor del parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-131">The sample returns a string where the return value is **Hello** followed by the value of the input parameter.</span></span>  
  
```  
Function SayHello(&sName As string) Returns string  
      &EOL = Char(10);  
      &sResult = "Hello " | &sName | &EOL;  
      Return &sResult;  
End-Function;  
```  
  
> [!NOTE]
>  <span data-ttu-id="8f4c8-132">Para modificar múltiples tablas al mismo tiempo (mediante un comando) puede crear otra interfaz de componente o un método definido por el usuario para la interfaz de componente.</span><span class="sxs-lookup"><span data-stu-id="8f4c8-132">To modify multiple tables at the same time (using one command) you can either create another component interface or create a component interface user-defined method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f4c8-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f4c8-133">See Also</span></span>  
 [<span data-ttu-id="8f4c8-134">Apéndice A: Métodos de interfaces de componentes</span><span class="sxs-lookup"><span data-stu-id="8f4c8-134">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)