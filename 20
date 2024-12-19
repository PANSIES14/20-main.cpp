#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

// Функция для объединения перекрывающихся интервалов
vector<vector<int>> mergeIntervals(vector<vector<int>>& intervals) {
    if (intervals.empty()) return {};

    // Сортируем интервалы по начальной точке
    sort(intervals.begin(), intervals.end());

    vector<vector<int>> merged;
    merged.push_back(intervals[0]); // Добавляем первый интервал

    for (int i = 1; i < intervals.size(); i++) {
        // Получаем последний добавленный интервал
        vector<int>& lastMerged = merged.back();

        // Проверяем, перекрываются ли текущий и последний интервалы
        if (intervals[i][0] <= lastMerged[1]) {
            // Объединяем интервалы
            lastMerged[1] = max(lastMerged[1], intervals[i][1]);
        } else {
            // Если не перекрываются, добавляем текущий интервал
            merged.push_back(intervals[i]);
        }
    }

    return merged;
}

int main() {
    vector<vector<int>> intervals = {{1, 3}, {2, 6}, {8, 10}, {15, 18}};
    
    vector<vector<int>> mergedIntervals = mergeIntervals(intervals);

    cout << "Объединенные интервалы: " << endl;
    for (const auto& interval : mergedIntervals) {
        cout << "[" << interval[0] << ", " << interval[1] << "] ";
    }
    cout << endl;

    return 0;
}
