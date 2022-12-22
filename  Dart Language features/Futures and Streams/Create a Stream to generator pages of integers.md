## GenerateDataService with Generator function.
#### Resources
[What are sync*, async*, yield and yield* in Dart](https://jelenaaa.medium.com/what-are-sync-async-yield-and-yield-in-dart-defe57d06381)


#### Example
```dart
class GenerateDataService {
  int recsPerPage = 15;
  int currPageIndex = 0;
  reset() {
    currPageIndex = 0;
  }
  Future<List<int>> getPage(Stream<int> genIndexes) async {
    List<int> result = [];
    await for (final value in genIndexes) {
      result.add(value);
    }
    currPageIndex++;
    int recNo = currPageIndex * recsPerPage;
    return result;
  }

  Stream<int> genIndexes() async* {
    int startIdx = currPageIndex * recsPerPage + 1 ;
    int lastIdx =  currPageIndex * recsPerPage +  recsPerPage;
    for (int i = startIdx; i <= lastIdx; i++) {
      yield i;
    }
  }

  Future<List<int>> generate() async {
    var stream = genIndexes();
    var list = await getPage(genIndexes());
    return list;
  }
}
```
