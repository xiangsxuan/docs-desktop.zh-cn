---
title: 转换的矩阵表示形式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- composite transformations
- transformations [Windows Forms], linear
- matrices
- translations in matrix representation
- transformations [Windows Forms], composite
- vectors
- linear transformations
- transformations [Windows Forms], matrix representation of
- transformations [Windows Forms], translation
- affine transformations
ms.assetid: 0659fe00-9e0c-41c4-9118-016f2404c905
ms.openlocfilehash: 24da407de24a924a68466e4301cc3f4a74cb2e94
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96971622"
---
# <a name="matrix-representation-of-transformations"></a><span data-ttu-id="74f42-102">转换的矩阵表示形式</span><span class="sxs-lookup"><span data-stu-id="74f42-102">Matrix Representation of Transformations</span></span>
<span data-ttu-id="74f42-103">M × n 矩阵是一组按 m 行和 n 列排列的数字。</span><span class="sxs-lookup"><span data-stu-id="74f42-103">An m×n matrix is a set of numbers arranged in m rows and n columns.</span></span> <span data-ttu-id="74f42-104">下图显示了几个矩阵。</span><span class="sxs-lookup"><span data-stu-id="74f42-104">The following illustration shows several matrices.</span></span>  
  
 <span data-ttu-id="74f42-105">![转换](./media/aboutgdip05-art04.gif "AboutGdip05_art04")</span><span class="sxs-lookup"><span data-stu-id="74f42-105">![Transformations](./media/aboutgdip05-art04.gif "AboutGdip05_art04")</span></span>  
  
 <span data-ttu-id="74f42-106">可以通过添加单个元素来添加大小相同的两个矩阵。</span><span class="sxs-lookup"><span data-stu-id="74f42-106">You can add two matrices of the same size by adding individual elements.</span></span> <span data-ttu-id="74f42-107">下图显示了矩阵添加的两个示例。</span><span class="sxs-lookup"><span data-stu-id="74f42-107">The following illustration shows two examples of matrix addition.</span></span>  
  
 <span data-ttu-id="74f42-108">![转换](./media/aboutgdip05-art05.gif "AboutGdip05_art05")</span><span class="sxs-lookup"><span data-stu-id="74f42-108">![Transformations](./media/aboutgdip05-art05.gif "AboutGdip05_art05")</span></span>  
  
 <span data-ttu-id="74f42-109">M × n 矩阵可以与 n × p 矩阵相乘，结果为 m × p 矩阵。</span><span class="sxs-lookup"><span data-stu-id="74f42-109">An m×n matrix can be multiplied by an n×p matrix, and the result is an m×p matrix.</span></span> <span data-ttu-id="74f42-110">第一个矩阵中的列数必须与第二个矩阵中的行数相同。</span><span class="sxs-lookup"><span data-stu-id="74f42-110">The number of columns in the first matrix must be the same as the number of rows in the second matrix.</span></span> <span data-ttu-id="74f42-111">例如，可以将4×2矩阵乘以2×3矩阵，以生成4×3矩阵。</span><span class="sxs-lookup"><span data-stu-id="74f42-111">For example, a 4×2 matrix can be multiplied by a 2×3 matrix to produce a 4×3 matrix.</span></span>  
  
 <span data-ttu-id="74f42-112">可以将矩阵的平面和行和列中的点视为向量。</span><span class="sxs-lookup"><span data-stu-id="74f42-112">Points in the plane and rows and columns of a matrix can be thought of as vectors.</span></span> <span data-ttu-id="74f42-113">例如， (2，5) 是包含两个组件的矢量， (3、7、1) 是包含三个组件的矢量。</span><span class="sxs-lookup"><span data-stu-id="74f42-113">For example, (2, 5) is a vector with two components, and (3, 7, 1) is a vector with three components.</span></span> <span data-ttu-id="74f42-114">两个矢量的点积定义如下：</span><span class="sxs-lookup"><span data-stu-id="74f42-114">The dot product of two vectors is defined as follows:</span></span>  
  
 <span data-ttu-id="74f42-115"> (a、b) • (c、d) = ac + bd</span><span class="sxs-lookup"><span data-stu-id="74f42-115">(a, b) • (c, d) = ac + bd</span></span>  
  
 <span data-ttu-id="74f42-116"> (a、b、c) • (d、e、f) = ad + 为 + cf</span><span class="sxs-lookup"><span data-stu-id="74f42-116">(a, b, c) • (d, e, f) = ad + be + cf</span></span>  
  
 <span data-ttu-id="74f42-117">例如， (2，3) 和 (5，4) 为 (2) # B6 5) + (3) # B10 4) = 22 的点积。</span><span class="sxs-lookup"><span data-stu-id="74f42-117">For example, the dot product of (2, 3) and (5, 4) is (2)(5) + (3)(4) = 22.</span></span> <span data-ttu-id="74f42-118"> (2、5、1) 和 (4，3，1)  (2) # B6 4) + (5) # B10 3) + (1) # B14 1) = 24 的点积。</span><span class="sxs-lookup"><span data-stu-id="74f42-118">The dot product of (2, 5, 1) and (4, 3, 1) is (2)(4) + (5)(3) + (1)(1) = 24.</span></span> <span data-ttu-id="74f42-119">请注意，两个矢量的点积是一个数字，而不是另一个矢量。</span><span class="sxs-lookup"><span data-stu-id="74f42-119">Note that the dot product of two vectors is a number, not another vector.</span></span> <span data-ttu-id="74f42-120">另请注意，仅当两个矢量具有相同数量的组件时，才可以计算点积。</span><span class="sxs-lookup"><span data-stu-id="74f42-120">Also note that you can calculate the dot product only if the two vectors have the same number of components.</span></span>  
  
 <span data-ttu-id="74f42-121">让 (i，j) 是第 i 行和 jth 列中的 matrix A 中的条目。</span><span class="sxs-lookup"><span data-stu-id="74f42-121">Let A(i, j) be the entry in matrix A in the ith row and the jth column.</span></span> <span data-ttu-id="74f42-122">例如， (3，2) 是矩阵 A 中第三行第2列的条目。</span><span class="sxs-lookup"><span data-stu-id="74f42-122">For example A(3, 2) is the entry in matrix A in the 3rd row and the 2nd column.</span></span> <span data-ttu-id="74f42-123">假设 A、B 和 C 是矩阵，而 AB = C。C 的项计算如下：</span><span class="sxs-lookup"><span data-stu-id="74f42-123">Suppose A, B, and C are matrices, and AB = C. The entries of C are calculated as follows:</span></span>  
  
 <span data-ttu-id="74f42-124">C (i，j) = (行 i) • (B 的 a 列 j) </span><span class="sxs-lookup"><span data-stu-id="74f42-124">C(i, j) = (row i of A) • (column j of B)</span></span>  
  
 <span data-ttu-id="74f42-125">下图显示了矩阵乘法的几个示例。</span><span class="sxs-lookup"><span data-stu-id="74f42-125">The following illustration shows several examples of matrix multiplication.</span></span>  
  
 <span data-ttu-id="74f42-126">![转换](./media/aboutgdip05-art06.gif "AboutGdip05_art06")</span><span class="sxs-lookup"><span data-stu-id="74f42-126">![Transformations](./media/aboutgdip05-art06.gif "AboutGdip05_art06")</span></span>  
  
 <span data-ttu-id="74f42-127">如果您将平面中的某个点视为1×2矩阵，则可以通过将该点与2×2矩阵相乘来转换该点。</span><span class="sxs-lookup"><span data-stu-id="74f42-127">If you think of a point in a plane as a 1×2 matrix, you can transform that point by multiplying it by a 2×2 matrix.</span></span> <span data-ttu-id="74f42-128">下图显示了应用到点 (2，1) 的多个转换。</span><span class="sxs-lookup"><span data-stu-id="74f42-128">The following illustration shows several transformations applied to the point (2, 1).</span></span>  
  
 <span data-ttu-id="74f42-129">![转换](./media/aboutgdip05-art07.gif "AboutGdip05_art07")</span><span class="sxs-lookup"><span data-stu-id="74f42-129">![Transformations](./media/aboutgdip05-art07.gif "AboutGdip05_art07")</span></span>  
  
 <span data-ttu-id="74f42-130">上图中显示的所有转换都是线性转换。</span><span class="sxs-lookup"><span data-stu-id="74f42-130">All of the transformations shown in the preceding figure are linear transformations.</span></span> <span data-ttu-id="74f42-131">某些其他转换（如转换）不是线性的，并且不能表示为2×2矩阵的乘法。</span><span class="sxs-lookup"><span data-stu-id="74f42-131">Certain other transformations, such as translation, are not linear, and cannot be expressed as multiplication by a 2×2 matrix.</span></span> <span data-ttu-id="74f42-132">假设要从点开始 (2，1) ，将其旋转90度，将其在 x 方向上转换为3个单位，并在 y 方向转换为4个单位。</span><span class="sxs-lookup"><span data-stu-id="74f42-132">Suppose you want to start with the point (2, 1), rotate it 90 degrees, translate it 3 units in the x direction, and translate it 4 units in the y direction.</span></span> <span data-ttu-id="74f42-133">可以通过使用矩阵乘法后跟矩阵加法实现此目的。</span><span class="sxs-lookup"><span data-stu-id="74f42-133">You can accomplish this by using a matrix multiplication followed by a matrix addition.</span></span>  
  
 <span data-ttu-id="74f42-134">![转换](./media/aboutgdip05-art08.gif "AboutGdip05_art08")</span><span class="sxs-lookup"><span data-stu-id="74f42-134">![Transformations](./media/aboutgdip05-art08.gif "AboutGdip05_art08")</span></span>  
  
 <span data-ttu-id="74f42-135">线性转换 (按 2 x 2 矩阵相乘) 后接 (添加1×2矩阵) 称为仿射转换。</span><span class="sxs-lookup"><span data-stu-id="74f42-135">A linear transformation (multiplication by a 2×2 matrix) followed by a translation (addition of a 1×2 matrix) is called an affine transformation.</span></span> <span data-ttu-id="74f42-136">将仿射转换存储在一对矩阵中的替代方法 (一个用于线性部分，另一个用于平移) ，用于在3×3矩阵中存储整个转换。</span><span class="sxs-lookup"><span data-stu-id="74f42-136">An alternative to storing an affine transformation in a pair of matrices (one for the linear part and one for the translation) is to store the entire transformation in a 3×3 matrix.</span></span> <span data-ttu-id="74f42-137">若要执行此操作，平面中的点必须存储在具有虚第三坐标的1×3矩阵中。</span><span class="sxs-lookup"><span data-stu-id="74f42-137">To make this work, a point in the plane must be stored in a 1×3 matrix with a dummy 3rd coordinate.</span></span> <span data-ttu-id="74f42-138">常见的方法是使所有第三个坐标等于1。</span><span class="sxs-lookup"><span data-stu-id="74f42-138">The usual technique is to make all 3rd coordinates equal to 1.</span></span> <span data-ttu-id="74f42-139">例如，点 (2，1) 由矩阵 [2 1 1] 表示。</span><span class="sxs-lookup"><span data-stu-id="74f42-139">For example, the point (2, 1) is represented by the matrix [2 1 1].</span></span> <span data-ttu-id="74f42-140">下图显示了一个仿射转换 (旋转90度;在 x 方向上转换3个单位，在 y 方向上4个单位的) 表示为按单一3×3矩阵的乘法。</span><span class="sxs-lookup"><span data-stu-id="74f42-140">The following illustration shows an affine transformation (rotate 90 degrees; translate 3 units in the x direction, 4 units in the y direction) expressed as multiplication by a single 3×3 matrix.</span></span>  
  
 <span data-ttu-id="74f42-141">![转换](./media/aboutgdip05-art09.gif "AboutGdip05_art09")</span><span class="sxs-lookup"><span data-stu-id="74f42-141">![Transformations](./media/aboutgdip05-art09.gif "AboutGdip05_art09")</span></span>  
  
 <span data-ttu-id="74f42-142">在前面的示例中，点 (2，1) 映射到点 (2，6) 。</span><span class="sxs-lookup"><span data-stu-id="74f42-142">In the preceding example, the point (2, 1) is mapped to the point (2, 6).</span></span> <span data-ttu-id="74f42-143">请注意，3 x 3 矩阵的第三列包含数字0，0，1。</span><span class="sxs-lookup"><span data-stu-id="74f42-143">Note that the third column of the 3×3 matrix contains the numbers 0, 0, 1.</span></span> <span data-ttu-id="74f42-144">这对于仿射转换的 3 x 3 矩阵总是如此。</span><span class="sxs-lookup"><span data-stu-id="74f42-144">This will always be the case for the 3×3 matrix of an affine transformation.</span></span> <span data-ttu-id="74f42-145">重要数字是第1列和第2列中的六个数字。</span><span class="sxs-lookup"><span data-stu-id="74f42-145">The important numbers are the six numbers in columns 1 and 2.</span></span> <span data-ttu-id="74f42-146">矩阵的左上2×2部分表示转换的线性部分，第三行中的前两个条目表示平移。</span><span class="sxs-lookup"><span data-stu-id="74f42-146">The upper-left 2×2 portion of the matrix represents the linear part of the transformation, and the first two entries in the 3rd row represent the translation.</span></span>  
  
 <span data-ttu-id="74f42-147">![转换](./media/aboutgdip05-art10.gif "AboutGdip05_art10")</span><span class="sxs-lookup"><span data-stu-id="74f42-147">![Transformations](./media/aboutgdip05-art10.gif "AboutGdip05_art10")</span></span>  
  
 <span data-ttu-id="74f42-148">在 GDI + 中，可以在对象中存储仿射转换 <xref:System.Drawing.Drawing2D.Matrix> 。</span><span class="sxs-lookup"><span data-stu-id="74f42-148">In GDI+ you can store an affine transformation in a <xref:System.Drawing.Drawing2D.Matrix> object.</span></span> <span data-ttu-id="74f42-149">由于表示仿射转换的矩阵的第三列始终 (0，0，1) ，因此，在构造对象时，只应在前两列中指定六个数字 <xref:System.Drawing.Drawing2D.Matrix> 。</span><span class="sxs-lookup"><span data-stu-id="74f42-149">Because the third column of a matrix that represents an affine transformation is always (0, 0, 1), you specify only the six numbers in the first two columns when you construct a <xref:System.Drawing.Drawing2D.Matrix> object.</span></span> <span data-ttu-id="74f42-150">语句 `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` 构造如上图所示的矩阵。</span><span class="sxs-lookup"><span data-stu-id="74f42-150">The statement `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` constructs the matrix shown in the preceding figure.</span></span>  
  
## <a name="composite-transformations"></a><span data-ttu-id="74f42-151">复合转换</span><span class="sxs-lookup"><span data-stu-id="74f42-151">Composite Transformations</span></span>  
 <span data-ttu-id="74f42-152">复合转换是一系列转换，一个后跟另一个。</span><span class="sxs-lookup"><span data-stu-id="74f42-152">A composite transformation is a sequence of transformations, one followed by the other.</span></span> <span data-ttu-id="74f42-153">请考虑以下列表中的矩阵和转换：</span><span class="sxs-lookup"><span data-stu-id="74f42-153">Consider the matrices and transformations in the following list:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="74f42-154">矩阵 A</span><span class="sxs-lookup"><span data-stu-id="74f42-154">Matrix A</span></span>|<span data-ttu-id="74f42-155">旋转90度</span><span class="sxs-lookup"><span data-stu-id="74f42-155">Rotate 90 degrees</span></span>|  
|<span data-ttu-id="74f42-156">矩阵 B</span><span class="sxs-lookup"><span data-stu-id="74f42-156">Matrix B</span></span>|<span data-ttu-id="74f42-157">在 x 方向上按系数2缩放</span><span class="sxs-lookup"><span data-stu-id="74f42-157">Scale by a factor of 2 in the x direction</span></span>|  
|<span data-ttu-id="74f42-158">Matrix C</span><span class="sxs-lookup"><span data-stu-id="74f42-158">Matrix C</span></span>|<span data-ttu-id="74f42-159">在 y 方向上转换3个单位</span><span class="sxs-lookup"><span data-stu-id="74f42-159">Translate 3 units in the y direction</span></span>|  
  
 <span data-ttu-id="74f42-160">如果首先使用由矩阵 [2 1 1] 表示的点 (2，1) ，然后再乘以 A、B、C，则点 (2，1) 将按照列出的顺序进行三次转换。</span><span class="sxs-lookup"><span data-stu-id="74f42-160">If we start with the point (2, 1) — represented by the matrix [2 1 1] — and multiply by A, then B, then C, the point (2, 1) will undergo the three transformations in the order listed.</span></span>  
  
 <span data-ttu-id="74f42-161">[2 1 1]ABC = [-2 5 1]</span><span class="sxs-lookup"><span data-stu-id="74f42-161">[2 1 1]ABC = [-2 5 1]</span></span>  
  
 <span data-ttu-id="74f42-162">不是将复合转换的三个部分存储在三个单独的矩阵中，而是可以将 A、B 和 C 相乘，以获取存储整个复合转换的单个3×3矩阵。</span><span class="sxs-lookup"><span data-stu-id="74f42-162">Rather than store the three parts of the composite transformation in three separate matrices, you can multiply A, B, and C together to get a single 3×3 matrix that stores the entire composite transformation.</span></span> <span data-ttu-id="74f42-163">假设 ABC = D。然后，将一个点乘以 D，就会得到与点相乘的结果，然后再乘以 B，然后按 C。</span><span class="sxs-lookup"><span data-stu-id="74f42-163">Suppose ABC = D. Then a point multiplied by D gives the same result as a point multiplied by A, then B, then C.</span></span>  
  
 <span data-ttu-id="74f42-164">[2 1 1]D = [-2 5 1]</span><span class="sxs-lookup"><span data-stu-id="74f42-164">[2 1 1]D = [-2 5 1]</span></span>  
  
 <span data-ttu-id="74f42-165">下图显示了矩阵 A、B、C 和 D。</span><span class="sxs-lookup"><span data-stu-id="74f42-165">The following illustration shows the matrices A, B, C, and D.</span></span>  
  
 <span data-ttu-id="74f42-166">![转换](./media/aboutgdip05-art12.gif "AboutGdip05_art12")</span><span class="sxs-lookup"><span data-stu-id="74f42-166">![Transformations](./media/aboutgdip05-art12.gif "AboutGdip05_art12")</span></span>  
  
 <span data-ttu-id="74f42-167">复合转换的矩阵可以通过乘以单个变换矩阵来形成，这意味着任何一系列仿射转换都可以存储在单个 <xref:System.Drawing.Drawing2D.Matrix> 对象中。</span><span class="sxs-lookup"><span data-stu-id="74f42-167">The fact that the matrix of a composite transformation can be formed by multiplying the individual transformation matrices means that any sequence of affine transformations can be stored in a single <xref:System.Drawing.Drawing2D.Matrix> object.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="74f42-168">复合转换的顺序很重要。</span><span class="sxs-lookup"><span data-stu-id="74f42-168">The order of a composite transformation is important.</span></span> <span data-ttu-id="74f42-169">通常，旋转，然后缩放，然后平移与缩放、旋转和平移不同。</span><span class="sxs-lookup"><span data-stu-id="74f42-169">In general, rotate, then scale, then translate is not the same as scale, then rotate, then translate.</span></span> <span data-ttu-id="74f42-170">同样，矩阵相乘的顺序也非常重要。</span><span class="sxs-lookup"><span data-stu-id="74f42-170">Similarly, the order of matrix multiplication is important.</span></span> <span data-ttu-id="74f42-171">通常，ABC 不同于背景。</span><span class="sxs-lookup"><span data-stu-id="74f42-171">In general, ABC is not the same as BAC.</span></span>  
  
 <span data-ttu-id="74f42-172"><xref:System.Drawing.Drawing2D.Matrix>类提供若干用于生成复合转换的方法： <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A> 、、、、 <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A> <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A> <xref:System.Drawing.Drawing2D.Matrix.Scale%2A> <xref:System.Drawing.Drawing2D.Matrix.Shear%2A> 和 <xref:System.Drawing.Drawing2D.Matrix.Translate%2A> 。</span><span class="sxs-lookup"><span data-stu-id="74f42-172">The <xref:System.Drawing.Drawing2D.Matrix> class provides several methods for building a composite transformation: <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>, <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>, <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>, <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>, <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>, and <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>.</span></span> <span data-ttu-id="74f42-173">下面的示例创建一个复合变换矩阵，该矩阵首先旋转30度，然后在 y 方向上按系数2缩放，然后在 x 方向平移5个单位：</span><span class="sxs-lookup"><span data-stu-id="74f42-173">The following example creates the matrix of a composite transformation that first rotates 30 degrees, then scales by a factor of 2 in the y direction, and then translates 5 units in the x direction:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 <span data-ttu-id="74f42-174">下图显示了矩阵。</span><span class="sxs-lookup"><span data-stu-id="74f42-174">The following illustration shows the matrix.</span></span>  
  
 <span data-ttu-id="74f42-175">![转换](./media/aboutgdip05-art13.gif "AboutGdip05_art13")</span><span class="sxs-lookup"><span data-stu-id="74f42-175">![Transformations](./media/aboutgdip05-art13.gif "AboutGdip05_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74f42-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74f42-176">See also</span></span>

- [<span data-ttu-id="74f42-177">坐标系和坐标转换</span><span class="sxs-lookup"><span data-stu-id="74f42-177">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="74f42-178">在托管 GDI+ 中使用变换</span><span class="sxs-lookup"><span data-stu-id="74f42-178">Using Transformations in Managed GDI+</span></span>](using-transformations-in-managed-gdi.md)
