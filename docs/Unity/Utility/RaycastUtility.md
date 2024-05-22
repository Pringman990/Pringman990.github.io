# Raycast Utility

Raycast Utility is used to send raycasts while the ray with ui.

Normal Unity raycast will go through UI elements. We dont always want this, so instead we use RaycastUtility.

## Example
```c#
 public GridCell GetCellFromWorldPosition(Ray aRay)
    {
        if (RaycastUtility.Raycast(aRay, out RaycastHit hit))
        {
            Vector3 worldPoint = hit.point;
            int x = Mathf.FloorToInt(worldPoint.x);
            int y = Mathf.FloorToInt(worldPoint.z);
            if (x < 0 || y < 0)
                return null;

            return m_GridList[x][y];
        }

        return null;
    }
};
```