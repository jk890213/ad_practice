<template>
    <section>
        <div class="container">
            <div class="text">
                <div class="title">
                    <h1 class="fadeInElement">中山藏富 林森藏美</h1>
                    <h2 class="fadeInElement"><span>Simple is Not Simple.</span><span>Simple is Beautiful.</span> </h2>
                </div>
                <div class="content">
                    <p class="fadeInElement">
                        <span>繁華城區 公園相伴</span>
                        <span>泊旅世界 心之所向</span>
                    </p>
                    <p class="fadeInElement">
                        <span>一座城市的繁華印記</span>
                        <span>一個輝煌時代的起點</span>
                        <span>以簡蘊美 生活無限</span>
                        <span>簡美，不簡單</span>
                    </p>
                    <p class="fadeInElement">
                        <span>「中山簡美」以家族之名</span>
                        <span>承載時代記憶與土地故事</span>
                        <span>從心打造回家的路</span>
                        <span>情繫老家到新家的心距離</span>
                    </p>
                </div>
            </div>
            <div class="pic">
                <div><img src="@/assets/images/description/s1-1.png" alt=""></div>
                <div><img src="@/assets/images/description/s1-2.jpg" alt=""></div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
section {
    padding: 0 12px;
    margin-bottom: 48px;

    @include desktops {
        margin-bottom: 160px;
    }

    .container {
        font-family: "Noto Serif TC", sans-serif;
        letter-spacing: 2px;
        margin: 0 auto;

        @include phone {
            max-width: 540px;
        }

        @include pad {
            max-width: 720px;
        }

        @include desktops {
            max-width: 960px;
            display: flex;
        }

        @include smallScreen {
            max-width: 1140px;
        }

        @include middleScreen {
            max-width: 1320px;
        }

        .text {
            @include desktops {
                display: flex;
                flex-direction: column;
                justify-content: space-around;
                width: 40%;
            }

            h1 {
                margin-bottom: 8px;
                font-size: 18px;
                font-weight: 600;

                @include desktops {
                    font-size: 18px;
                }

                @include smallScreen {
                    font-size: 20px;
                }

                @include middleScreen {
                    font-size: 30px;
                }
            }

            h1.fadeInElement.show {
                @include fadeAndMoveUpAnimation()
            }

            h2,
            p {
                display: flex;
                flex-direction: column;

                @include desktops {
                    font-size: 14px;
                }

                @include smallScreen {
                    font-size: 16px;
                }

                @include middleScreen {
                    font-size: 18px;
                }
            }

            h2.fadeInElement.show {
                @include fadeAndMoveUpAnimation(.2s)
            }

            p span {
                margin-bottom: 8px;
            }


            p.fadeInElement.show {
                &:first-child {
                    @include fadeAndMoveUpAnimation(.3s)
                }

                &:nth-child(2) {
                    @include fadeAndMoveUpAnimation(.4s)
                }

                &:last-child {
                    @include fadeAndMoveUpAnimation(.5s)
                }
            }
        }



        .pic {
            div {
                &:first-child {
                    margin-bottom: 4px;

                    @include desktops {
                        text-align: end;
                        margin-bottom: 20px;
                    }

                    img {
                        @include desktops {
                            width: 80%;
                        }
                    }


                }

                img {
                    width: 100%;
                }
            }
        }
    }

}
</style>