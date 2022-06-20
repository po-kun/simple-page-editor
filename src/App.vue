<template>
    <div class="container" id="box">
        <div class="row min-vh-100">
            <div class="col-3 border min-h-screen vh-100 pb-5 overflow-auto">
                <div class="form-group">
                    <label class="mt-5 mb-2">ページタイトル</label>
                    <input class="form-control" type="text" name="left" v-on:focusIn="highlight"
                        v-on:focusOut="highlightOut" v-model="message" />
                </div>
                <div class="form-group">
                    <label class="mt-5 mb-2">ページの説明</label>
                    <textarea class="form-control" type="textarea" name="left" v-model="description" />
                </div>
                <div class="form-group">
                    <label class="mt-5 mb-2">動画並びを選択</label>
                    <select class="form-select" v-model="selectedLayout" name="opts"
                        aria-label="Default select example">
                        <option value="3">4つ並び</option>
                        <option value="4">3つ並び</option>
                        <option value="6">2つ並び</option>
                        <option value="12">1つ並び</option>
                    </select>
                </div>

                <div class="row mt-5 p-4 px-1 border m-2">
                    <div class="col">
                        <h5>コンテンツの選択・編集</h5>
                        <div class="form-group">
                            <label class="mb-2">〇〇のタイトル</label>
                            <input class="form-control" type="text" name="left" v-model="movie1" />
                        </div>
                        <div class="form-group">
                            <label class="mt-5 mb-2">〇〇のタイトル</label>
                            <input class="form-control" type="text" name="left" v-model="movie2" />
                        </div>
                        <div class="form-group">
                            <label class="mt-5 mb-2">〇〇のタイトル</label>
                            <input class="form-control" type="text" name="left" v-model="movie3" />
                        </div>
                        <div class="form-group">
                            <label class="mt-5 mb-2">〇〇のタイトル</label>
                            <input class="form-control" type="text" name="left" v-model="movie4" />
                        </div>
                        
                        <div class="form-group">
                            <button class="mt-5 w-100 btn btn-outline-secondary">動画をえらぶ</button>
                        </div>
                    </div>
                </div>


                <div class="form-group">
                    <button class="mt-5 w-100 btn btn-outlined btn-success">保存</button>
                </div>
            </div>
            <div class="col pt-5 px-5">
                <h1>{{ message }}</h1>
                <p v-html="brValue"></p>

                <div class="row">
                    <div class="mb-3" v-bind:class="classOfImages">
                        <span class="fw-bold">{{ movie1 }}</span>
                        <img class="img-fluid" src="https://placehold.jp/3d4070/ffffff/1920x1080.png?text=Video" alt="">
                    </div>
                    <div class="mb-3" v-bind:class="classOfImages">
                        <span class="fw-bold">{{ movie2 }}</span>
                        <img class="img-fluid" src="https://placehold.jp/3d4070/ffffff/1920x1080.png?text=Video" alt="">
                    </div>
                    <div class="mb-3" v-bind:class="classOfImages">
                        <span class="fw-bold">{{ movie3 }}</span>
                        <img class="img-fluid" src="https://placehold.jp/3d4070/ffffff/1920x1080.png?text=Video" alt="">
                    </div>
                    <div class="mb-3" v-bind:class="classOfImages">
                        <span class="fw-bold">{{ movie4 }}</span>
                        <img class="img-fluid" src="https://placehold.jp/3d4070/ffffff/1920x1080.png?text=Video" alt="">
                    </div>
                </div>
            </div>

        </div>
    </div>
</template>

<script>
export default {
    data: function () {
        return {
            message: '新年のご挨拶',
            description: '2022年度 インタビュー動画一覧',
            selectedLayout: '3',
            movie1: '新年のご挨拶',
            movie2: '新年のご挨拶2',
            movie3: '新年のご挨拶3',
            movie4: '新年のご挨拶4'
        }
    },
    computed: {
        brValue: function () {
            return this.description.replace(/\n/g, "<br />")
        },
        classOfImages: function () {
            return `col-lg-${this.selectedLayout}`;
        }
    },
    methods: {
        highlight: function () {

        },
        highlightOut: function () {

        },
    }
}
</script>

<style lang="scss" scoped>
</style>
