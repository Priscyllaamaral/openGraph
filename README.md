# openGraph


            <script>
            export default {
              data() {
                return {
                  message: "Olá. Venha para nosso site!",
                  siteName : "Anron",
                  desc : "Rodada da moda",
                  title: "Você no rumo do sucesso",
                  tel: 5581995143219,
                  url:"https://www.namoda.com.vc/",
                  //img : 'https://w7.pngwing.com/pngs/980/712/png-transparent-computer-icons-user-avatar-avatar-heroes-silhouette-50x50.png'
                  img: 'https://neilpatel.com/wp-content/uploads/2019/05/imagem-de-tela-de-uma-url.jpeg'
                  //img: 'https://www.shutterstock.com/image-vector/link-url-icon-260nw-1226618155.jpg'
                }
              },
              methods:{
                 setOg(){


                  const ogSite = document.createElement('meta');
                  ogSite.setAttribute('property', 'og:site_name');
                  ogSite.content = this.siteName;
                  document.head.appendChild(ogSite);

                  const ogTitle = document.createElement('meta');
                  ogTitle.setAttribute('property', 'og:title');
                  ogTitle.content = this.title;
                  document.head.appendChild(ogTitle);

                  const ogDesc = document.createElement('meta');
                  ogDesc.setAttribute('property', 'og:description');
                  ogDesc.content = this.desc;
                  document.head.appendChild(ogDesc);

                  const ogImg = document.createElement('meta');
                  //aqui
                  ogImg.setAttribute('name', 'imagem');
                  ogImg.setAttribute('property', 'og:image');
                  ogImg.content = this.img;
                  document.head.appendChild(ogImg);

                  const ogType = document.createElement('meta');
                  ogType.setAttribute('property', 'og:type');
                  ogType.content = "website";
                  document.head.appendChild(ogType);

                  const ogImgType = document.createElement('meta');
                  ogImgType.setAttribute('property', 'og:image:type');
                  ogImgType.content = "image/jpeg";
                  document.head.appendChild(ogImgType);

                  const ogUrl = document.createElement('meta');
                  ogUrl.setAttribute('property', 'og:url');
                  ogUrl.content = this.url;
                  document.head.appendChild(ogUrl);

                  const ogImgW = document.createElement('meta');
                  ogImgW.setAttribute('property', 'og:image:width');
                  ogImgW.content = 300;
                  document.head.appendChild(ogImgW);

                  const ogImgH = document.createElement('meta');
                  ogImgH.setAttribute('property', 'og:image:height');
                  ogImgH.content = 300;
                  document.head.appendChild(ogImgH);


                },

                setImg(image){
                  const metaDesc =  document.querySelector('meta[name="imagem"]');
                  metaDesc.content = image;
                  this.img = image;


                }

              },
              computed :{
                  whats(){
                    const encod = encodeURIComponent(this.message);
                    //return 'https://api.whatsapp.com/send?text='+this.message;
                    //return 'https://api.whatsapp.com/send?text=Ol%C3%A1%2C%20!'
                    return 'https://api.whatsapp.com/send?text='+encod;
                    //return 'https://www.google.com/'
                    //return 'https://neilpatel.com/br/blog/url-o-que-e/'
                    //return 'https://api.whatsapp.com/send?text=${encod}'
                    //return 'https://wa.me/${tel}/?text=${encod}'
                  }
                },
              created(){

                },
              mounted(){
                this.setOg();


              }
            }
            </script>


            <template>
              <header>

                <v-app>



                  <Tela />


                  <v-container>
                    <Botao> 
                      <template v-slot:new3>
                        Aperte aqui 
                      </template>  
                    </Botao>

                   <Botao color="red"> 
                      <template v-slot:new3> Aperte aqui!! </template>  
                    </Botao>
                </v-container>


                <div>
                  <h1>
                    <a :href="whats" @click="setImg('https://www.shutterstock.com/image-vector/link-url-icon-260nw-1226618155.jpg')" target="_blank"> 
                      <img :src="img" alt="WhatsApp">
                    </a>
                    {{message}}
                  </h1>
                </div>




              </v-app>
              </header>


            </template>
