<script lang="ts">
</script>

<div class="chat-container">
	<div class="header">
		<span>トークルーム１</span>
		<img class="btn config" src="/icons/setting.png" alt="プロフィール設定ボタン" />
	</div>
	<div class="message-view">
		<div class="message-box you">
			<img class="avatar" src="/icons/account_circle.png" alt="user1" />
			<div class="message-area">
				<span class="name"> user1 </span>
				<span class="message-text"> 外が寒いのに、電車が熱いｗｗｗ </span>
			</div>
		</div>
		<div class="message-box me">
			<img class="avatar" src="/icons/account_circle.png" alt="user1" />
			<div class="message-area">
				<span class="name"> user2 </span>
				<span class="message-text"> 草 </span>
			</div>
		</div>
	</div>
	<div class="input-view">
		<img class="btn add-photo" src="/icons/add_photo.png" alt="写真を追加" />
		<input class="input-text" type="text">
		<img class="btn submit" src="/icons/send.png" alt="送信">
	</div>
</div>

<style>
	/* チャット全体のレイアウトと高さの設定 */
	.chat-container {
		display: flex;
		flex-direction: column;
		height: 100vh;
	}

	/* ヘッダーの設定 */
	.header {
		justify-content: space-between;
		background-color: #4bce53;
		color: white;
		display: flex;
        flex-direction: row;
        align-items: center;
        flex-grow: 1;
        padding: 5px;
        width: 100%;
        height: 60px;

		span {
            font-weight: bold;
            font-size: large;
            padding: 10px;
        }

	}

	/* メッセージ領域のサイズと背景色の設定 */
	.message-view {
		flex-grow: 2;
		background-color: #83cbcd;
		height: 90vh;
	}

	/* メッセージとアイコンの配置の設定 */
	.message-box {
		display: flex;
		width: 100%;
		/* アイコンサイズの設定 */
		.avatar {
			width: 50px;
			height: 50px;
		}

	}
	.me {
		flex-direction: row-reverse;
	}

	/* ユーザー名とメッセージを縦並びにする設定 */
	.message-area {
		margin-left: 5px; /* アイコンとメッセージの間を少しあける */
        display: flex;
        flex-direction: column;
	}

	/* 名前の文字色を変更する設定 */
	.name {
		color: whitesmoke;
	}

	/* メッセージを吹き出しにする設定 */
	.message-text {
		padding: 5px;
        text-align: center;
		border: solid 1px lightgray;
		border-radius: 15px;
		background-color: whitesmoke;
	}

	.input-view {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		background-color: #4bce53;
		.input-text {
			flex-grow: 2;
		}
	}

	.btn {
		width: 50px;
		height: 50px;
	}

</style>
