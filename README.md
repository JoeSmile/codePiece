# codePiece
some useful js code 

/**
 * 判断一个节点是否包含另一个节点
 */
_contains(root, el) {
    if (root === el) {
        return true
    }
    if (root.contains && el.nodeType === 1) {
        return root.contains(el)
    }
    if (root.compareDocumentPosition) {
        return root === el || !!(root.compareDocumentPosition(el) & 16)
    }
    while ((el = el.parentNode))
        if (el === root) return true
    return false
}
